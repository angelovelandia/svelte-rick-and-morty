<script>
    export let character;
</script>

<div class="character">
    <img src={character.image} alt={character.name} />
    <h2>{character.name}</h2>
    <div class="item">
        <p>Status: </p>
        <p>{character.status}</p>
    </div>
    <div class="item">
        <p>Species: </p>
        <p>{character.species}</p>
    </div>
</div>
