<script>
export let title, poster, year, index
</script>

<style>
    article{
        border: 1px solid #eee;
        border-radius: 4px;
        padding: 16px;
    }

    h3{
        font-size: 24px;
        margin-bottom: 4px;
    }

</style>

    <article>
        <p>#{index}</p>
        <h3>{title}</h3>
        <img alt={title} src={poster}/>
        <p>{year}</p>
    </article>