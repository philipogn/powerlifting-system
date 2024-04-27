<script>
	import '../app.pcss';
	import { AppBar } from '@skeletonlabs/skeleton';
</script>

<AppBar border="-" background="blue">
	<svelte:fragment slot="lead">
		<div class="brand">
			<h1>Power lifting App</h1>
		</div>
		</svelte:fragment>
	<svelte:fragment slot="trail">
		<nav>
			<a href="/">Home</a>
			<a href="/warmUp">Warm Up calculation tool</a>
			<a href="/about">About</a>
		</nav>
	</svelte:fragment>

</AppBar>


<slot></slot>
