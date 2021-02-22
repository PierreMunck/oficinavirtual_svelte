<script>
    export let titleList = 'titleList';
    export let listItem = [];
    export let open = false;
</script>
<section class={open ? "visible" : 'invisible'}>
<h2>{titleList}</h2>
    <ul>
        {#each listItem as item}
        <li>{item.value}</li>
        {/each}
    </ul>
</section>

<style>
	h2 {
        color: chartreuse;
    }

    .visible {
       padding : 10px;
    }

    .invisible {
        display: none;
    }
</style>