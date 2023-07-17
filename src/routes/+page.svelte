<script>
    import Masonry from 'svelte-bricks'

    let nItems = 10
    $: items = [...Array(nItems).keys()]

    let [minColWidth, maxColWidth, gap] = [200, 200, 20]
    let width, height
</script>

<nav>
    <h1>k3fans</h1>
    <div class="bar"></div>
</nav>

<h2>Pictures:</h2>

<Masonry 
    let:item
    {items}
    {minColWidth}
    {maxColWidth}
    {gap}
    bind:width
    bind:height
>
    <img src={`/${item}.jpg`} alt="k_3alpha" width="200">
</Masonry>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700;900&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&display=swap');

    :global(body) {
        margin: 0;
        font-family: 'Roboto', sans-serif;
    }
    nav > h1 {
        text-align: center;
        font-family: 'Great Vibes', cursive;
        margin-block: 0.5rem;
        font-size: 5rem;
        color: #4881ea;
    }
    h2 {
        text-align: center;
        font-family: 'Great Vibes', cursive;
        margin-block: 1rem;
        font-size: 3rem;
        color: #4881ea;
    }
    img {
        border-radius: 10px;
    }
    .bar {
        height: 2rem;
        background-color: #4881ea;
    }
</style>
