<script>
    export let mode = 'S';

    function toggle() {
        mode = mode === 'S' ? 'M' : 'S';
        window.document.body.classList.toggle('dark-mode')
    }
</script>

<div class="row">
    <div class="contenedorNav">
        <header class="header">
            <div class="imgName">
                <a href="/" class="imgName">
                    <div>
                        <img class="imgName_CustomImage" src="images/imgPerfil.JPG" alt="Manuel Quiroga">
                    </div>
                    <div>
                        <span>Manuel Quiroga</span>
                    </div>
                </a>
            </div>
            <div class="nav_links">
                <ul>
                    <li>
                        <a href="/aboutme">Acerca de</a>
                        <a href="/courses">Cursos</a>
                        <a href="/projects">Proyectos</a>
                        <a href="/contactme">Contacto</a>
                    </li>
                </ul>
            </div>
            <div class="social-icons">
                <a href="https://www.linkedin.com/in/manuelhquiroga" target="_blank" role="button" class="custom_Icon"><i class="fa-brands fa-linkedin" style="color: white;"></i></a>
                <a href="https://github.com/ManuelQuiroga03" target="_blank" role="button" class="custom_Icon"><i class="fa-brands fa-square-github" style="color: white;"></i></a>
                <div role="button" class="custom_Icon" on:click={toggle}>
                    {#if mode === 'S'}
                        <i class="fa-regular fa-sun" style="color: white;"></i>
                    {:else if mode === 'M'}
                        <i class="fa-solid fa-moon" style="color: white;"></i>
                    {/if}
                </div>
            </div>
        </header>
    </div>
</div>

<style>
    ul{
        margin: 0;
        padding: 0;
        list-style: none;
    }
    li{
        text-decoration: none;
    }
    a{
        text-decoration: none;
        color: white;
        margin-right: 15px;
        font-size: 20px;
        font-weight: 600;
    }
    .contenedorNav{
        margin-left: auto;
        margin-right: auto;
        align-items: center;
        background-color: #091A28;
    }
    .header{
        display: flex;
        justify-content: space-between;
        margin-left: 10px;
        margin-right: 20px;
        padding-top: 1rem;
        padding-bottom: 1rem;
        align-items: center;
    }
    /* Sección Imagen y nombre */
    .imgName{
        display: flex;
        gap: 16px;
        align-items: center;
        color: white;
    }
    .imgName_CustomImage{
        border-radius: 50%;
        width: 50px;
        height: 50px;
        object-fit: cover;
    }
    .social-icons{
        display: flex;
        justify-content: end;
        gap: 15px;
    }
    .custom_Icon{
        font-size: 1.5rem;
        background-color: transparent;
        border: none;
    }
</style>