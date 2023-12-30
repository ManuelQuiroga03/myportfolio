<script>
    import Swal from 'sweetalert2';

    let frmData = {
        fname: '',
        lname: '',
        email: '',
        mob: '',
        job: '',
        ans: '',
    }

    let sending = false;

    let errors = {};

    function handleSubmit() {
        errors = {};

        if (!frmData.fname.trim()) {
            errors.fname = '¡Por favor, ingresa tu nombre!';
        }
        if (!frmData.lname.trim()) {
            errors.lname = '¡Por favor, ingresa tu apellido!';
        }
        if (!frmData.email.trim()) {
            errors.email = '¡Por favor, ingresa tu correo!';
        }
        if (!frmData.mob.trim()) {
            errors.mob = '¡Por favor, ingresa tu teléfono!';
        }
        if (!frmData.job.trim()) {
            errors.job = '¡Por favor, ingresa tu asunto!';
        }
        if (!frmData.ans.trim()) {
            errors.ans = '¡Por favor, ingresa tu mensaje!';
        }

        if (Object.keys(errors).length === 0) {
            sending = true;
            setTimeout(() => {
                sending = false; 
                showSuccessAlert(); 
            }, 3000);
        }

    }

    function handleInput(event){
        errors = {...errors, [event.target.name]: ''};
    }

    function showSuccessAlert() {
        Swal.fire({
            title: 'Envío exitoso',
            text: 'Tu mensaje ha sido enviado correctamente.',
            icon: 'success',
            timer: 3000, 
            timerProgressBar: true,
            showConfirmButton: false
        }).then(() => {
            Object.keys(frmData).forEach(key => frmData[key] = '');
        });
        setTimeout(() => {
            goToHome();
        },3000);
    }

    function goToHome() {
        window.location.href = '/contentme';
    }
</script>

<div class="container-fluid  mx-auto" style="margin-top: 100px;">
    <div class="row d-flex justify-content-center">
        <div class="col-xl-7 col-lg-8 col-md-9 col-11 text-center">
            <h3>Escríbeme</h3>
            <p class="blue-text">¡Hola! ¿En qué puedo ayudarte? Por favor, déjanos tu mensaje aquí...</p>
            <div class="card">
                <!-- <h5 class="text-center mb-4"></h5> -->
                <form class="form-card" on:submit|preventDefault={handleSubmit}>
                    <div class="row justify-content-between text-left">
                        <div class="form-group col-sm-6 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="fname">Nombre<span class="text-danger"> *</span></label> 
                            <input type="text" id="fname" name="fname" placeholder="" bind:value={frmData.fname} on:input={handleInput}> 
                            {#if errors.fname}
                                <span class="text-danger">{errors.fname}</span>
                            {/if}
                        </div>
                        <div class="form-group col-sm-6 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="lname">Apellidos<span class="text-danger"> *</span></label> 
                            <input type="text" id="lname" name="lname" placeholder="" bind:value={frmData.lname} on:input={handleInput}> 
                            {#if errors.lname}
                                <span class="text-danger">{errors.lname}</span>
                            {/if}
                        </div>
                    </div>
                    <div class="row justify-content-between text-left">
                        <div class="form-group col-sm-6 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="email">Correo electrónico<span class="text-danger"> *</span></label>
                            <input type="text" id="email" name="email" placeholder="" bind:value={frmData.email} on:input={handleInput}>
                            {#if errors.email}
                                <span class="text-danger">{errors.email}</span>
                            {/if} 
                        </div>
                        <div class="form-group col-sm-6 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="mob">Teléfono<span class="text-danger"> *</span></label> 
                            <input type="text" id="mob" name="mob" placeholder="" bind:value={frmData.mob} on:input={handleInput}>
                            {#if errors.mob}
                                <span class="text-danger">{errors.mob}</span>
                            {/if} 
                        </div>
                    </div>
                    <div class="row justify-content-between text-left">
                        <div class="form-group col-sm-6 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="job">Asunto<span class="text-danger"> *</span></label> 
                            <input type="text" id="job" name="job" placeholder="" bind:value={frmData.job} on:input={handleInput}>
                            {#if errors.job}
                                <span class="text-danger">{errors.job}</span>
                            {/if} 
                        </div>
                    </div>
                    <div class="row justify-content-between text-left">
                        <div class="form-group col-12 flex-column d-flex"> 
                            <label class="form-control-label px-3" for="ans">¿Te gustaría platicar sobre algo?<span class="text-danger"> *</span></label> 
                            <input type="text" id="ans" name="ans" placeholder="" bind:value={frmData.ans} on:input={handleInput}>
                            {#if errors.ans}
                                <span class="text-danger">{errors.ans}</span>
                            {/if} 
                        </div>
                    </div>
                    <div class="row justify-content-end">
                        <div class="form-group col-sm-6" style="text-align: end;"> 
                            <button type="submit" class="btn-block btn-primary" on:click={handleSubmit}>
                                {#if sending}
                                    <div class="spinner-border text-success" role="status">
                                        <span class="sr-only">Loading...</span>
                                    </div>
                                {:else}
                                    Enviar
                                {/if}
                            </button> 
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
</div>

<style>
    
.card {
    padding: 30px 40px;
    margin-top: 60px;
    margin-bottom: 60px;
    border: none !important;
    box-shadow: 0 6px 12px 0 rgba(0, 0, 0, 0.2)
}

.blue-text {
    color: #00BCD4
}

.form-control-label {
    margin-bottom: 0
}

input,
textarea,
button {
    padding: 8px 15px;
    border-radius: 5px !important;
    margin: 5px 0px;
    box-sizing: border-box;
    border: 1px solid #ccc;
    font-size: 18px !important;
    font-weight: 300
}

input:focus,
textarea:focus {
    -moz-box-shadow: none !important;
    -webkit-box-shadow: none !important;
    box-shadow: none !important;
    border: 1px solid #00BCD4;
    outline-width: 0;
    font-weight: 400
}

.btn-block {
    text-transform: uppercase;
    font-size: 15px !important;
    font-weight: 400;
    height: 43px;
    cursor: pointer
}

.btn-block:hover {
    color: #fff !important
}

button:focus {
    -moz-box-shadow: none !important;
    -webkit-box-shadow: none !important;
    box-shadow: none !important;
    outline-width: 0
}
</style>