<script lang="ts">
    import Crash from "./missions/t_crash.svelte";
    import Data from "./missions/t_data.svelte";
    import Fire from "./missions/t_fire.svelte";
    import Materials from "./missions/t_materials.svelte";
    import Seed from "./missions/t_seed.svelte";
    import Water from "./missions/t_water.svelte";

    let tabs = [
        { name: "Crash Site Surveying", comp: Crash },
        { name: "Data Extraction", comp: Data },
        { name: "Fire Suppression", comp: Fire },
        { name: "Materials Identification", comp: Materials },
        { name: "Seed Planting", comp: Seed },
        { name: "Water Sampling", comp: Water }
    ];

    let cur = tabs[0];
</script>

<div class="text">
    <link rel="preload" href="https://docs.google.com/document/d/e/2PACX-1vSFLHpf8p2p0zhl4L2aKseYKU9o91be04eaQBqMURGEkOEwkBC1QqDe3Sgg2ovlxJfIMtZKckG7TKGE/pub?embedded=true" as="document">
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
        display:block;
        background-color: white;
        margin: 0;
    }
</style>
