<script lang="ts">
    import Index from "$lib/Index.svelte";
    import IndexWeb from "$lib/IndexWeb.svelte";
    import { page } from "$app/stores";;
</script>

<svelte:head>
    <title>VELMA</title>
</svelte:head>

{#if $page.url.pathname == "/enes100-velma/public-tools/"}
    <div class="page">
        <slot></slot>
    </div>
{:else if $page.url.pathname == "/enes100-velma/website/"}
    <div class="page">
        <IndexWeb></IndexWeb>
        <slot></slot>
    </div>
{:else}
    <div class="page">
        <Index></Index>
        <slot></slot>
    </div>
{/if}