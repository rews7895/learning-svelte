<script>
  export let numbers;
  $: sum = numbers.reduce((acc, n) => acc + n);
</script>

<div>numbers ar {numbers.join(', ')}</div>
<div>sum is {sum}</div>
