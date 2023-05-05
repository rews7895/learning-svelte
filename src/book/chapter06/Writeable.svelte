<script>
  // @ts-nocheck

  import {writable} from 'svelte/store';

  export const dogStore = writable([], async set => {
    const res = await fetch('/dogs');
    const dogs = await res.json();
    set(dogs);
    return () => {};
  });
</script>
