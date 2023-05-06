<script>
  import {element} from 'svelte/internal';

  let name = '';
  const focus = element => element.focus();
</script>

<input bind:value={name} use:focus />
