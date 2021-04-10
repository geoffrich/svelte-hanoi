<script>
	import Tower from './Tower.svelte';

	let numberOfDisks = 3;
	let source = 'Tower A';
	let destination = 'Tower C';
	let intermediate = 'Tower B';

	$: isValidInput = numberOfDisks > 0;
</script>

<main>
<h1>Tower of Hanoi</h1>
<label for="disks">Number of Disks</label>
<input bind:value={numberOfDisks} type="number" id="disks" aria-describedby={isValidInput ? null : "error"}>

{#if isValidInput}
<h2 id="list-heading">How to move {numberOfDisks} disks from {source} to {destination}</h2>
<ol aria-labelledby="list-heading">
	<Tower disk={numberOfDisks} {source} {intermediate} {destination} />
</ol>
{:else}
<p id="error">Please enter a positive number.</p>
{/if}
</main>
