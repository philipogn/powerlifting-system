<script lang="ts">
	import { goto } from '$app/navigation';
	import '../app.pcss';
	import { AppBar, popup, type PopupSettings } from '@skeletonlabs/skeleton';
	import { computePosition, autoUpdate, offset, shift, flip, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, offset, shift, flip, arrow });


	const popupFeatured: PopupSettings = {
		// Represents the type of event that opens/closed the popup
		event: 'click',
		// Matches the data-popup value on your popup element
		target: 'popupFeatured',
		// Defines which side of your trigger the popup will appear
		placement: 'bottom',
	};
					
			
</script>

<AppBar background="bg-surface-100-800-token">
	<svelte:fragment slot="lead">
		<div class="brand">
			<h1>POWELIFTING APP</h1>
		</div>
		</svelte:fragment>
	<svelte:fragment slot="trail">
		<nav class="nav">
			<a href="/">HOME</a>

			<button class="tool-button" use:popup={popupFeatured}>TOOLS</button>
			<div class="card p-4 w-72 shadow-xl" data-popup="popupFeatured">
				<div><a href="/tools/warmUp" class="popup-link">Warm Up calculation tool</a></div>
				<div><a href="/tools/oneRepMax" class="popup-link">One Rep Max calculation tool</a></div>
				<div class="arrow bg-surface-100-800-token" />
			</div>
					
				

			<a href="/about">ABOUT</a>
		</nav>
	</svelte:fragment>

</AppBar>

<style>
	.brand {
		font-size: 40px;
		font-weight: bold;
	}

	.nav { /* nav bar styling */
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 20px;
		margin: 0 auto;
	}

	.nav a{ /*nav bar link styling */
		font-weight: bold;
		font-size: 25px;
		justify-content: center;
		text-decoration: none;
		padding: 20px;
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

	.tool-button {
		font-size: 25px;
		font-weight: bold;
		justify-content: center;
		text-decoration: none;
		padding: 20px;
		display: flex;
		align-items: center;
		gap: 5px;
		border-radius: 5px; /* round corners */
		transition: background-color 0.3s, color 0.3s; /* transition for hover effects */
		color: rgb(0, 0, 0);
		margin: 0 auto;
	}

	.tool-button:hover { /* nav hover effect */
        background-color: hsl(0, 78%, 43%); /* color on hover */
        color: white;
    }

	.popup-link {
		font-size: 20px;
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
	/* WIP FOR POPUP STYLING */
	

</style>


<slot></slot>
