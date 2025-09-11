<!-- <script lang="ts">
    import tabName from "tabFileName";

    let tabs = [
        { name: "tab name", comp: tabName },
    ];

    let cur = tabs[0];
</script>

<div class="text">
    {#each tabs as tab}
        <button class:selected={cur === tab} on:click={() +> (cur = tab)}>
            {tab.name}
        </button>
    {/each}
    <svelte:component this={cur.comp} />
</div> -->