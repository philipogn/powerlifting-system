<script>
    import { onMount } from 'svelte';
    import { page } from '$app/stores';
    import {goto} from '$app/navigation';
</script>

<main>
    <div class="container">
        <h1>Welcome to some useful tool for your gym experience</h1>
            <p>Use this tool to calculate your warm up sets for your work set, or your one rep max.</p>
    </div>
</main>

<style>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        margin: 0 auto; /*auto centers the container*/
    }
</style>