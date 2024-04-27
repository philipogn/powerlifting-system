<script>
	import { goto } from '$app/navigation';
	import '../app.pcss';
	import { AppBar } from '@skeletonlabs/skeleton';
</script>

<AppBar background="bg-surface-100-800-token">
	<svelte:fragment slot="lead">
		<div class="brand">
			<h1>Power lifting App</h1>
		</div>
		</svelte:fragment>
	<svelte:fragment slot="trail">
		<nav class="nav">
			<a href="/">Home</a>
			<a href="/warmUp">Warm Up calculation tool</a>
			<button on:click={() => goto('/warmUp')}>Warm Up</button>

			<a href="/about">About</a>
		</nav>
		<a href="/" class="card p-4">Link</a>
	</svelte:fragment>

</AppBar>

<style>
	.nav { /* nav bar styling */
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.nav a{ /*nav bar link styling */
		justify-content: center;
		text-decoration: none;
		padding: 10px;
		display: flex;
		align-items: center;
		gap: 5px;
		border-radius: 5px; /* round corners */
		transition: background-color 0.3s, color 0.3s; /* transition for hover effects */
		color: rgb(0, 0, 0);
		margin: 0 auto;
	}

	.nav a:hover { /* nav hover effect */
        background-color: hsl(0, 78%, 43%); /* color on hover */
        color: white;
    }

</style>


<slot></slot>
