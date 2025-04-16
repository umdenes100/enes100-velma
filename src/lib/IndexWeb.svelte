<script>
    import "../lib/global.css";
    import { base } from "$app/paths";

    let visible = true;
    function toggleVisible() {
        visible = !visible;
    }
</script>

<div class="index">
    {#if visible}
        <div class="directory">
            <h3>Menu</h3>
            <!-- <p>
                <a href="{base}">Home</a><br>
                <a href="{base}/store">School Store</a><br>
                <a href="{base}/milestone">Milestone 7</a><br>
                <a href="/maintenance">Maintenance</a><br />
                <a href="{base}/tools">Tool Check</a><br>
                <a href="/queue">Help Queue</a>
                <a href="{base}/docs">Documentation</a><br>
            </p> -->
            <ul>
                <li>
                    <a data-sveltekit-replacestate href={base}>Home</a>
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/docs"
                        >Documentation</a
                    >
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/store"
                        >School Store</a
                    >
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/tools"
                        >Tool Check</a
                    >
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/website"
                        >Website</a
                    >
                </li>
            </ul>
        </div>
    {/if}
    <button id="bb" class="flipped" on:click={toggleVisible}>
        <img id="M" src="{base}/img/M.png" alt="M" />
    </button>
</div>

<style>
    li {
        line-height: 30px;
        padding: 0% 15%;
    }
    a {
        font-weight: bold;
        color: white;
        margin: 5px;
    }
    a:hover {
        color: red;
    }
    h3 {
        font-size: 30px;
        margin: 20px 0px -10px 0px;
        padding: 0% 10%;
    }
    .index {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-basis: content;
        position: absolute;
        flex-direction: row;
        top: 10vh;
        min-height: 240px;
    }
    .directory {
        height: auto;
        width: auto;
        background-color: #121b21;
        color: white;
        border: 0.5vw solid white;
        width: 16vw;
        border-left: none;
        min-width: 170px;
    }
    button {
        background: none;
        border: none;
    }
    #bb {
        margin-left: 2%;
    }
    #M {
        height: 40px;
        margin: 0 2vw;
    }
    #bb.flipped {
        height: 4vh;
        transform: rotateY(180deg);
    }
    ul {
        list-style: none;
        padding: 0;
    }
</style>
