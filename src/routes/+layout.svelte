<script>
	import Menu from '$lib/components/menu.svelte';
	import Sidebar from '$lib/components/sidebar.svelte';
</script>

<div class="app-layout">
	<Menu />
	<div class="main-content">
		<Sidebar />
		<main>
			<slot />
		</main>
	</div>
</div>

<style>
	.app-layout {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		background-color: var(--background-color);
	}

	.main-content {
		display: flex;
		flex: 1;
	}

	main {
		flex: 1;
		padding: 1rem;
		overflow-y: auto;
	}

	@media (max-width: 1024px) {
		main {
			width: 100%;
		}
	}
</style>