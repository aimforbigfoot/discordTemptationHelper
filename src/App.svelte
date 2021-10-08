<script>
	export let totalCount = 0;
	export let failedCount = 0;
	export let succeedCount = 0;

	const increaseTotal = () => totalCount++;
	const increaseFail = () => {
		failedCount++;
		increaseTotal();
	}
	const increaseSucceed = () => {
		succeedCount++;
		increaseTotal();
	}

</script>


<main>
	<h1>Total times tempted: {totalCount}</h1>

	<h2>Times opened Discord: {failedCount}</h2>
	<h2>Times ignored Discord: {succeedCount}</h2>

	<div>
		<button on:click={increaseFail} >I opened discord</button>
		<button on:click={increaseSucceed}> I did not open discord but I wanted to</button>
	</div>
	
</main>

<style>
	*{
		padding: 0%;
		text-align: center;
	}
	body{

	}
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}
	button{
		padding: 1em;
	}

</style>