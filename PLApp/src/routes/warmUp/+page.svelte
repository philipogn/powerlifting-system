<script>
    // import { onMount } from 'svelte';
    // import { page } from '$app/stores';
    // import {goto} from '$app/navigation';

    let weight = 0;
    const rep5 = 0.6;
    const rep3 = 0.75;
    const rep1 = 0.9;
    let weight5 = 0;
    let weight3 = 0;
    let weight1 = 0;

    function roundingQuarter() { // round to nearest 2.5
        weight5 = 2.5 * Math.ceil(weight5/2.5);
        weight3 = 2.5 * Math.ceil(weight3/2.5);
        weight1 = 2.5 * Math.ceil(weight1/2.5);
    }

    function warmUpCalc(weight) {
        weight5 = weight * rep5;
        weight3 = weight * rep3;
        weight1 = weight * rep1;
        roundingQuarter();
    }

    // function warmUpWeight(weight) {
    //     warmUpCalc(weight);
    // }
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
            <button on:click={warmUpCalc(weight)}>Submit</button>
        </div>
        <div class="right">
            <h2>Warm Up Sets</h2>
            <p>5 Reps: {weight5}</p>
            <p>3 Reps: {weight3}</p>
            <p>1 Rep: {weight1}</p>
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