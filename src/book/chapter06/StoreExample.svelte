<script>
  import {onDestroy} from 'svelte';
  import {dogStore} from '../../store';

  let dogs;
  const unsubscribe = dogStore.subscribe(value => (dogs = value));
  onDestroy(unsubscribe);
</script>
