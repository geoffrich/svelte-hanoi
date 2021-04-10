<script>
  export let source;
  export let intermediate;
  export let destination;
  export let disk;

  import Step from './Step.svelte';
</script>

{#if disk === 1}
<Step {disk} {source} {destination} />
{:else}
<svelte:self disk={disk - 1} source={source} intermediate={destination} destination={intermediate} />
<Step {disk} {source} {destination} />
<svelte:self disk={disk - 1} source={intermediate} intermediate={source} destination={destination} />
{/if}
