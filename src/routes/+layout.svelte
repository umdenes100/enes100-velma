<script lang="ts">
    import Index from "$lib/Index.svelte";
    import IndexWeb from "$lib/IndexWeb.svelte";
    import { page } from "$app/stores";;
</script>

<svelte:head>
    <title>VELMA</title>
</svelte:head>

{#if $page.url.pathname != "/velma/website/"}
    <div class="page">
        <Index></Index>
        <slot></slot>
    </div>
{:else}
    <div class="page">
        <IndexWeb></IndexWeb>
        <slot></slot>
    </div>
{/if}
