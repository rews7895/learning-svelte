<script>
  let breed = 'Whippet';

  async function getDogs() {
    const url =
      'https://dog.ceo/api/breed/' + `${breed.toLowerCase()}/images/random/1`;
    const res = await fetch(url);
    if (!res.ok || res.status === 404) return [];
    const json = await res.json();
    return json.message;
  }

  let dogsPromise = getDogs();
</script>

<label>
  breed
  <input bind:value={breed} />
</label>
<button on:click={() => (dogsPromise = getDogs())}>Get Image</button>

{#await dogsPromise}
  <div>Waiting for dogs...</div>
{:then imageUrls}
  {#each imageUrls as url}
    <div><img src={url} alt="dog" /></div>
  {:else}
    <div>Not found</div>
  {/each}
{/await}
