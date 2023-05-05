<script>
  import Sum from './SumChild.svelte';

  let size = 3;
  $: numbers = Array(size)
    .fill()
    .map((_, i) => i + 1);
</script>

<div>
  <label>
    size
    <input type="number" bind:value={size} />
  </label>

  <Sum {numbers} />
</div>
