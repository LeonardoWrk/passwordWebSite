<script lang="ts">
	import { page } from '$app/stores';

	const navs = [
		{
			title: 'about',
			href: '/about'
		},
		{
			title: 'dowload',
			href: '/dowload'
		}
	];

	$: routeId = $page.route.id;
</script>

<nav>
	<div class="container">
		<div class="title">Projeto</div>
		<ul>
			{#each navs as { title, href }}
				<li>
					<a class="hover" {href} class:active={routeId == href}>{title}</a>
				</li>
			{/each}
		</ul>
	</div>
</nav>

<style>
	nav {
		padding: 0.1em;
		background-color: #5e5b5b;
	}
	.container {
		width: 75%;
		margin: 0 auto;
		padding: 20px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.title {
		font-size: 1.7em;
		color: #eddede;
	}
	ul {
		position: relative;
		list-style: none;
		margin: 0;
		display: flex;
	}
	li {
		margin: 0 10px;
		font-size: 1.5em;
	}
	a {
		text-decoration: none;
		color: #eddede;
	}
	.active {
		color: white;
	}
	.hover:hover {
		color: azure;
	}

	/* Adiciona uma regra de mídia para dispositivos menores para empilhar os elementos verticalmente */
	@media (max-width: 768px) {
		.container {
			flex-direction: column;
			align-items: flex-start;
		}

		.title {
			margin-bottom: 10px;
		}
	}
</style>
