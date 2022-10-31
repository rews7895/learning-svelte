<script>
  let color = 'yellow';
  let isMorning = true;
</script>

<div class="component-split">
  <h3>If</h3>
  {#if color === 'yellow'}
    <div>Nice color!</div>
  {:else if color === 'green'}
    <div>That's Okay too.</div>
  {:else}
    <div>Questionable choice.</div>
  {/if}

  {#if isMorning}
    <h4>Good Morning!</h4>
    <p>There is a lot on your plate today.</p>
  {/if}
</div>
