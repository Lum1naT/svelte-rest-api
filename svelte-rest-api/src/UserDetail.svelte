<script>
  export let userId;
  var url = 'http://127.0.0.1:8000/users/' + userId + '/';
  const fetchImage = (async () => {
    const response = await fetch(url);
    return await response.json();
  })();
</script>

{#await fetchImage}
  <p>...waiting</p>
{:then data}
  <h1>Username: {data.username}</h1>
  <h2>Email: {data.email}</h2>
{:catch error}
  <p>An error occurred!</p>
{/await}
