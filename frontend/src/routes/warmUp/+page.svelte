<script>
    // import { onMount } from 'svelte';
    // import { page } from '$app/stores';
    // import {goto} from '$app/navigation';

    let weight = 0;
    const rep5 = 0.6;
    const rep3 = 0.75;
    const rep1 = 0.9;

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
        <div class="left">
            <div class="warm-up__weight">
                <label for="weight">Weight</label>
                <input type="number" id="weight" bind:value={weight} />
            </div>
            <button on:click={warmUpWeight(weight)}>Submit</button>
        </div>
        <div class="right">
            <h2>Warm Up Sets</h2>
            <p>5 Reps: {warmUp5(weight)}</p>
            <p>3 Reps: {warmUp3(weight)}</p>
            <p>1 Rep: {warmUp1(weight)}</p>
        </div>
    </div>
</main>


<style>
    .container {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .left {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .right {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .warm-up__weight {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>