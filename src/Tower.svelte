<script>
	export let disk, source, intermediate, destination;
</script>

{#if disk === 1}
<li>Move disk {disk} from {source} to {destination}</li>
{:else}
<svelte:self disk={disk - 1} source={source} intermediate={destination} destination={intermediate} />
<li>Move disk {disk} from {source} to {destination}</li>
<svelte:self disk={disk - 1} source={intermediate} intermediate={source} destination={destination} />
{/if}
