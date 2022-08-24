<script>
	import MainMenu from '$lib/components/menues/MainMenu.svelte';
	import { page } from '$app/stores';
	import lazyload from 'vanilla-lazyload';
  	import { browser } from '$app/env';

  if (browser && !document.lazyloadInstance) {
    document.lazyloadInstance = new lazyload();
  }
  


</script>

<header>
	<hgroup>
		<a href="/">
			<h1 class:small={$page.url.pathname !== '/'}>Demo</h1>
		</a>
	</hgroup>

	<MainMenu />
</header>


<slot />


<footer class="container">
<hr>

	<p>Copyright &#169; <a href="#" target="_blank">Rights Owner</a>, {new Date().getFullYear()}</p>

</footer>

<style>
	:global(:root) {
		--spacing-unit: 4px;
		--color-background: #e5e5e5;
		--color-text-primary: #212121;
		--color-text-secondary: #5a5a5a;
	}

	:global(*) {
		scroll-margin-top: 2em;
		box-sizing: border-box;
	}

	:global(body) {
		
		/* max-width: 75ch; */
		padding: calc(var(--spacing-unit) * 8);
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu',
			'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;

		background-color: var(--color-background);
		color: var(--color-text-primary);
		line-height: 1.51;
		font-size: 18px;
	}

	:global(main) {
		margin: 0 auto;
		width: 100%;
		max-width: 75ch;
	}

	:global(a, a:visited, a:active) {
		text-decoration: none;
		color: var(--color-text-primary);
		font-weight: 700;
	}

	:global(a:hover) {
		text-decoration: underline;
	}

	.small {
		font-size: 1.6rem;
	}

	footer {
		margin-top: calc(var(--spacing-unit) * 8);
	}

	hgroup h1, hgroup p {
		margin: 0px;
		text-align: center;
	}

	:global(img) {
		max-width: 100%;
		height: auto;
	}

	:global(.icon.icon-link){
		display: inline-block;
		display: none;
		width:1em;
		height:1em;
		float: left;
		/* <!-- License: CC Attribution. Made by seyfdesigner: https://www.figma.com/@seyfdesigner --> */
		background-image: url('data:image/svg+xml;charset=UTF-8,<svg width="24px" height="24px" viewBox="0 0 24 24" id="magicoon-Filled" xmlns="http://www.w3.org/2000/svg"><g id="link-Filled"><path id="link-Filled-2" data-name="link-Filled" class="cls-1" d="M20.545,10.467l-1.839,1.84a1,1,0,0,1-1.414-1.414l1.839-1.84a2.965,2.965,0,0,0,0-4.186,3.027,3.027,0,0,0-4.184,0l-3.36,3.36a2.046,2.046,0,0,0-.267.316,2.943,2.943,0,0,0,.268,3.87,1,1,0,0,1-1.415,1.414,4.915,4.915,0,0,1-.5-6.42,3.792,3.792,0,0,1,.5-.594l3.36-3.36a4.959,4.959,0,0,1,7.013,7.014Zm-8.132-.294a1,1,0,0,0,0,1.414,2.928,2.928,0,0,1,.688,3.1,2.827,2.827,0,0,1-.688,1.088l-3.36,3.36a3.027,3.027,0,0,1-4.184,0,2.965,2.965,0,0,1,0-4.186l1.839-1.84a1,1,0,1,0-1.414-1.414l-1.839,1.84a4.959,4.959,0,1,0,7.013,7.014l3.359-3.359a4.813,4.813,0,0,0,1.163-1.849,4.963,4.963,0,0,0-1.163-5.166A1,1,0,0,0,12.413,10.173Z"/></g></svg>');
		background-size: contain;
		background-repeat: no-repeat;
		background-position: center;
	}
</style>
