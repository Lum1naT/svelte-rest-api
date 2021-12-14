<script>
  const fetchImage = (async () => {
    const response = await fetch('http://127.0.0.1:8000/users/');
    return await response.json();
  })();
</script>

{#await fetchImage}
  <p>...waiting</p>
{:then data}
  <ul>
    {#each data.results as user}
      <li><a href="/user/{user.url.split('/')[4]}">{user.username}</a></li>
    {/each}
  </ul>
{:catch error}
  <p>An error occurred!</p>
{/await}
