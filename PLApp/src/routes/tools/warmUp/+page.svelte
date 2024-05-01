<script lang="ts">

    let weight:number = 0;
    const rep5 = 0.6;
    const rep3 = 0.75;
    const rep1 = 0.9;
    let weight5 = 0;
    let weight3 = 0;
    let weight1 = 0;

    function roundingQuarter() { // round to nearest 2.5
        weight5 = 2.5 * Math.round(weight5/2.5);
        weight3 = 2.5 * Math.round(weight3/2.5);
        weight1 = 2.5 * Math.round(weight1/2.5);
    }

    function warmUpCalc(weight: number) {
        weight5 = weight * rep5;
        weight3 = weight * rep3;
        weight1 = weight * rep1;
        roundingQuarter();
    }
    
</script>

<main>
    <div class="container">

        <div class="left">
            <h1>Warm Up</h1>
            <br>
            <label for="weight">Weight (KGs)</label>
            <input class="input-box" id="weight" bind:value={weight} />
            <button on:click={() => warmUpCalc(weight)}>Submit</button>
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
        padding: 5%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 auto; /*auto centers the container*/

    }

    .left {
        flex: 1; /*split the container into 2 equal parts*/
        display: flex;
        justify-content: left;
        align-items: center;
        flex-direction: column;
    }

    .right {
        flex: 1; /*split the container into 2 equal parts*/
        display: flex;
        justify-content: right;
        align-items: center;
        flex-direction: column;
    }

    .input-box {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding: 1%;
        border: 1px solid #ccc; /* add a border around the input box */
        border-radius: 5px; /* add rounded corners*/
        /* margin-bottom: 1%; */
        text-align: left;
    }
</style>