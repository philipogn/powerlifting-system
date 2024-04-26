<script>
    import { onMount } from 'svelte';
    import { page } from '$app/stores';
    import {goto} from '$app/navigation';

    let weight = 0;
    let rep5 = 0.6;
    let rep3 = 0.75;
    let rep1 = 0.9;

    function warmUp5(weight) {
        return weight * rep5;
    }

    function warmUp3(weight) {
        return weight * rep3;
    }

    function warmUp1(weight) {
        return weight * rep1;
    }
    // Your first warm up set should be done with 60% of your work set for 5 reps. 
    // Second should be done with 75-80% of your work set for 3 reps
    // final warm up set should be done with 90% for 1 rep.
    
</script>

<main>
    <div class="container">
        <h1>Warm Up</h1>
        <div class="warm-up">
            <div class="warm-up__weight">
                <label for="weight">Weight</label>
                <input type="number" id="weight" bind:value={weight} />
            </div>
            <button on:click={warmUpWeight(weight)}>Submit</button>
        </div>
    <p><a href="/home">Home</a><p/>
</main>


<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
