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
            <br>
            <label for="weight">Weight (KGs)</label>
            <input class="input-box" id="weight" bind:value={weight} />
            <br>
            <label for="reps">Reps</label>
            <input class="input-box" id="reps" bind:value={reps} />
            
            <button class="submit-button" on:click={() => oneRepMax(weight, reps)}>Submit</button>
        </div>

        <div class="right">
            <h2>Estimated One Rep Max</h2>
            <p>1RM: {oneRepMaxWeightRounded}</p>
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

    .submit-button {
        text-decoration: none;
        padding: 15px 25px;
        border-radius: 5px; /* rounded corners */
        background-color: hsl(0, 27%, 62%);
        color: antiquewhite;
        transition: background-color 0.3s, color 0.3s, box-shadow 0.3s; /* transition for hover effects */
        margin: 0 auto; /* centering button */  
        justify-content: center;
		display: flex;
		align-items: center;
		gap: 5px;
    }

    .submit-button:hover {
        background-color: hsl(4, 88%, 47%);
        color: white;
        box-shadow: 0 0 10px 0 hsl(11, 87%, 47%);
    }
</style>