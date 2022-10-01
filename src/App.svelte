<script>
  import Character from './lib/Character.svelte'
  
  let characters = [];
  let url = "https://rickandmortyapi.com/api/character?page="
  let page = 1;
  async function loadCharacters() {
    const response = await fetch(`${url}${page}`);
    const data = await response.json();
    console.log(data);
    characters = data.results;
    console.log(characters);
  }
  loadCharacters();

  function nextPage() {
    page++;
    loadCharacters();
  }

  function prevPage() {
    page--;
    loadCharacters();
  }
</script>

<h1 class="title">Rick And Morty Svelte!</h1>


<div class="container">
  
  <div class="btns">
    <button class="btn" on:click={prevPage} disabled={page === 1}>Previus</button>
    <p class="page">{page}</p>
    <button class="btn" on:click={nextPage}>Next</button>
  </div>

  <div class="grid">
    {#each characters as character}
      <Character character={character} />
    {/each}
  </div>
</div>
