<script>
let value = ''
let response = []
import Movie from "./Movie.svelte";

function handleInput(event) {
    value = event.target.value
}

$: if (value.length > 3) {
    response = fetch(`https://www.omdbapi.com/?s=${value}&apikey=422350ff`)
    .then(res => !res.ok() && new Error('Algo ha pasado con el fetch de datos de la api'))
        .then(res => res.json())
        .then(apiresponse => apiresponse.Search || [] )
}
</script>

<input placeholder="Search movies ..." type="text" name="input" id="input" value={value} on:input={handleInput}>

{#await response}
<strong>Loading...</strong>
{:then movies}
    <!-- Sin destructurar -->
    <!-- {#each response as movie} -->
    <!-- Destructurado -->
    {#each movies as {Title, Poster, Year}, index}
    <Movie
    index = {index}
    title = {Title}
    poster = {Poster}
    year = {Year}
    />
    {:else}
    <strong>
        No tenemos películas
    </strong>
    {/each}
    {:catch error}
    <p>X ha habido un error</p>
{/await}
