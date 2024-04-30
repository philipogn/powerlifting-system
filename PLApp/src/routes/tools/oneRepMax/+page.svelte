<script lang="ts">

    let weight:number = 0;
    let reps:number = 0;
    let oneRepMaxWeight = 0;
    let oneRepMaxWeightRounded = 0;

    function oneRepMax(weight: number, reps: number) {
        // 1rm = weight / ( 1.0278 - 0.0278 × reps )
        oneRepMaxWeight = weight / (1.0278 - 0.0287 * reps);
        oneRepMaxWeightRounded = Math.round(oneRepMaxWeight);
        return oneRepMaxWeightRounded;
    }
    
</script>

<main>
    <div class="container">

        <div class="left">
            <h1>One Rep Max Calculator</h1>
            <label for="weight">Weight (KGs)</label>
            <div class="input">
                <input type="number" id="weight" bind:value={weight} />
            </div>
            <label for="reps">Reps</label>
            <div class="input">
                <input type="number" id="reps" bind:value={reps} />
            </div>
            <button on:click={() => oneRepMax(weight, reps)}>Submit</button>
        </div>

        <div class="right">
            <h2>Estimated One Rep Max</h2>
            <p>1RM: {oneRepMaxWeightRounded}</p>
        </div>

    </div>
</main>


<style>
    .container {
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

    .input {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
</style>