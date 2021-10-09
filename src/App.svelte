<script>
	export let totalCount = 0;
	export let failedCount = 0;
	export let succeedCount = 0;
	export let avoidThing = "Thing To Avoid";
	export let verbToUse = "open";
	let toShowSettings = true;

	const increaseTotal = () => totalCount++;
	const increaseFail = () => {
		failedCount++;
		increaseTotal();
	}
	const increaseSucceed = () => {
		succeedCount++;
		increaseTotal();
	}
	const doneSettings = (val) =>{
		console.log(val, " was  called")
		toShowSettings = val;
	}
</script>


<main>
	<h1>Total times tempted by {avoidThing}: {totalCount}</h1>

	<h2>Times tempted {avoidThing}: {failedCount}</h2>
	<h2>Times ignored {avoidThing}: {succeedCount}</h2>

	<div>
		<button on:click={increaseFail} >I {verbToUse}ed {avoidThing}</button>
		<button on:click={increaseSucceed}> I did not {verbToUse} {avoidThing}</button>
	</div>

	{#if toShowSettings }
	<input bind:value={avoidThing} placeholder="what are you trying to avoid" />
	<input bind:value={verbToUse} placeholder="verb to use?" />
	<br>
	<button on:click={() => doneSettings(false)}>Done with settings</button>
	{/if}

</main>

<style>
	*{
		padding: 0%;
		text-align: center;
	}
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}
	button{
		padding: 1em;
	}
	input{
		padding: 0.5em;
		width: 50%;
	}

</style>