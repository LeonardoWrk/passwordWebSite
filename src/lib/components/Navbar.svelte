<script lang="ts">
	import { page } from '$app/stores';

	$: routeId = $page.route.id;
</script>

<nav>
	<div class="container">
		<h1>Projeto</h1>
		<ul>
			<li>
				<a href="/about" class="hover" class:active={routeId == '/about'}>About</a>
			</li>
			<li>
				<a href="/dowload" class="hover" class:active={routeId == '/dowload'}>Dowload</a>
			</li>
		</ul>
	</div>
</nav>

<style>
	nav {
		padding: 0.1em;
		background-color: #5e5b5b;
	}
	.container {
		display: flex;
	}
	ul {
		display: flex;
		margin: 0;
		margin-left: auto;
		list-style: none;
	}
	li {
		margin: 20px;
		font-size: 1.5em;
	}
	h1 {
		font-size: 1.7em;
		margin: 20px;
		color: #eddede;
	}
	a {
		text-decoration: none;
		color: #eddede;
	}
	.active {
		color: #06062d;
	}
	.hover:hover {
		color: azure;
	}
</style>
