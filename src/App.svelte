<!-- Portafolio.svelte -->
<script>
  
  import { Router, Route } from 'svelte-routing';
	import Aboutme from './Content/aboutme.svelte';
	import Navbar from './Header/navbar.svelte';
	import Footer from './Footer/footer.svelte';
	import Contentme from './Content/contentme.svelte';
  import Contactme from './Content/contactme.svelte';

  export let url = '';

</script>

<main>
	<div class="">
		<div class="contenedor">
			<div class="navbar-container">
        <Navbar></Navbar>
      </div>
      <Router url= "{url}">
        <Route path=''><Contentme/></Route>
        <Route path='/aboutme'><Aboutme/></Route>
        <Route path='/contactme'><Contactme/></Route>
      </Router>
		
			<Footer></Footer>
		</div>
	</div>
</main>

<style>
	.contenedor{
		margin: 0;
		/* display: flex;
		flex-direction: column; */ 
		width: 100%;
		min-height: 100vh;
	}
	
	.navbar-container {
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 1000; 
	}
	:global(body) {
		background-color: #FFFFFF;
		color: #000;
		transition: background-color 0.3s
	}
	:global(body.dark-mode) {
		background-color: #1d3040;
		color: #bfc2c7;
	}
  :global(p.dark-mode){
    color: #FFFFFF;
  }

</style>
