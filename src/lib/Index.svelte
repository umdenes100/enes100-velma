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
                    <a data-sveltekit-replacestate href="{base}">Home</a>
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/docs">Documentation</a>
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/store">School Store</a>
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/tools">Tool Check</a>
                </li>
                <li>
                    <a data-sveltekit-replacestate href="{base}/website">Website</a>
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
    }
    .index {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-basis: content;
    }
    .directory {
        height: auto;
        width: auto;
        background-color: rgba(255, 255, 255, 0.2);
        color: white;
        border: 0.5vw solid white;
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
    }
    #bb.flipped {
        height: 4vh;
        transform: rotateY(180deg);
    }
    ul {
        list-style: none;
        padding: 0;
    }
    @media (max-width: 900px) {
        .index {
            flex-direction: column;
        }
        .directory {
            min-height: 12vh;
            width: 80vw;
            border-top: none;
            text-align: justify;
        }
        #M {
            margin: 2vw 0;
        }
        li {
            padding: 0% 10%;
        }
        h3 {
            padding: 0% 5%;
        }
    }
    @media (min-width: 900px) {
        .index {
            flex-direction: row;
        }
        .directory {
            width: 16vw;
            border-left: none;
        }
        #M {
            margin: 0 2vw;
        }
        li {
            padding: 0% 15%;
        }
        h3 {
            padding: 0% 10%;
        }
    }
</style>
