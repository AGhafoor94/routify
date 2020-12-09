<script>
  export let pokemon;
  const url = `https://pokeapi.co/api/v2/pokemon/${pokemon}`;
</script>

{pokemon}

{#await fetch(url).then((res) => res.json())}
  Loading
  {pokemon}...
{:then response}
  <img src={response.sprites.front_default} alt={pokemon} />
{/await}
