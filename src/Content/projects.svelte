<script>
    
</script>

<div class="row" style="margin-top: 100px; width: 100%;">
    <div class="col">
        <div class="container">
            <div class="row">
                <div class="col-md-3">
                    <div class="card-sl">
                        <div class="card-image">
                            <img src="images/coffe.jpg" alt="">
                        </div>
                        <div class="card-heading">
                            Blog de Café
                        </div>
                        <div class="card-text">
                            Blog de cafe donde aplicamos conocimiento de HTML, CSS y diseño responsivo
                        </div>
                        <a href="https://luminous-blogdecafe.netlify.app/" target="_blank" class="card-button">Visitar</a>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="card-sl">
                        <div class="card-image">
                            <img src="images/store.jpg" alt="">
                        </div>
                        <div class="card-heading">
                            Tienda en línea
                        </div>
                        <div class="card-text">
                            Tienda en línea hecha con REACT, JS y CSS, consumiendo una API gratuita pública
                        </div>
                        <a href="https://astounding-gaufre-bffc2c.netlify.app/" target="_blank" class="card-button">Visitar</a>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="card-sl">
                        <div class="card-image">
                            <img src="images/todolist.jpg" alt="">
                        </div>
                        <div class="card-heading">
                            To do List
                        </div>
                        <div class="card-text">
                            Aplicación en Angular, con HTML, JavaScript y CSS para registro de tareas
                        </div>
                        <a href="https://warm-bavarois-335167.netlify.app/" target="_blank" class="card-button">Visitar</a>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="card-sl">
                        <div class="card-image">
                            <img src="images/imgPerfil.JPG" alt="">
                        </div>
                        <div class="card-heading">
                            Mi portafolio
                        </div>
                        <div class="card-text">
                            Aplicación hecha con Svelte, HTML y CSS, es el sitio que vemos en este momento
                        </div>
                        <a id="ultimoBoton" href="https://cool-tarsier-ac0029.netlify.app/" target="_blank" class="card-button disabled">Visitar</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
    .card-sl {
        margin-bottom: 10px;
        border-radius: 8px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }

    .card-image{
        text-align: center;
    }

    .card-image img {
        max-height: 250px;
        max-width: 100%;
        margin-top: 10px;
        margin-bottom: 10px;
        border-radius: 8px;
    }

    .card-heading {
        font-size: 18px;
        font-weight: bold;
        background: #fff;
        padding: 10px 15px;
    }

    .card-text {
        padding: 10px 15px;
        background: #fff;
        font-size: 14px;
        color: #636262;
    }

    .card-button {
        display: flex;
        justify-content: center;
        padding: 10px 0;
        width: 100%;
        background-color: #1F487E;
        color: #fff;
        border-radius: 0 0 8px 8px;
    }

    .card-button:hover {
        text-decoration: none;
        background-color: #1D3461;
        color: #fff;
    }

    .card-button.disabled {
        pointer-events: none;
        background-color: #ccc; /* Cambia el color de fondo a uno más claro */
        color: #666; /* Cambia el color del texto a uno más oscuro */
        cursor: default; /* Cambia el cursor a predeterminado */
        opacity: 0.6; /* Añade una opacidad para indicar deshabilitado */
        text-decoration: none !important; /* Elimina cualquier decoración de texto */
    }

</style>