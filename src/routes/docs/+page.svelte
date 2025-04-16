<script>
    import Missions from "./t_missions.svelte";
    import ProjDetails from "./t_proj_details.svelte";

    let tabs = [
        { name: "Mission Specifications", comp: Missions },
        { name: "Project Details", comp: ProjDetails },
    ];

    let cur = tabs[0];
</script>

<div class="text">
    {#each tabs as tab}
        <button class:selected={cur === tab} on:click={() => (cur = tab)}>
            {tab.name}
        </button>
    {/each}
    <svelte:component this={cur.comp} />
</div>

<style>
    button {
        cursor: pointer;
        padding: 0.5rem 1rem;
        border: 1px solid transparent;
        margin-bottom: -1px;
        background-color: #fff;
        border-bottom-color: #abc;
        font: inherit;
        font-size: smaller;
        color: black;
    }
    button.selected {
        border-top-right-radius: 8px;
        border-top-left-radius: 8px;
        border-top-width: 8px;
        border-color: #e21833 #abc #fff;
    }
    .text {
        font-size: 1rem;
        padding: 2rem;
        display: block;
        width: 90%;
    }
</style>
