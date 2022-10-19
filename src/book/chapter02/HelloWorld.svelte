<script>
  let color = 'red';
  let name = 'world';
  let upper = false;
  /**
   * $: => 리액티브 구문으로 해당 구문이 참조하는 변수값이 변경되면 다시 실행됩니다.
   */
  $: greeting = `Hello ${name}`;
  $: casedGreeting = upper ? greeting.toUpperCase() : greeting;
</script>

<div class="component-split">
  <label for="name">Name</label>
  <input type="text" id="name" bind:value={name} />
  <br />
  <label for="color">Color</label>
  <input type="text" id="color" bind:value={color} />
  <br />
  <br />
  <div class="swatch" style="background-color: {color}" />
  <label>
    <input type="checkbox" bind:checked={upper} />
    Uppercase
  </label>

  <h1 style="color: {color}">{casedGreeting}</h1>
</div>

<style>
  .swatch {
    display: inline-block;
    height: 20px;
    width: 20px;
  }
</style>
