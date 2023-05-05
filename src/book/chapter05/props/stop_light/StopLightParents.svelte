<script>
  import StopLightChild from './StopLightChild.svelte';
  let go = false;
</script>

<StopLightChild />
<StopLightChild on />
<StopLightChild on={go} />
<button on:click={() => (go = !go)}>Toggle</button>
