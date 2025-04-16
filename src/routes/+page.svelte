<script>
    import { base } from "$app/paths";
</script>

<div class="text" id="Text">
    <h1>VELMA</h1>
    <div class="apps">
        <div class="app">
            <a rel="preload" href="{base}/store">
                <img src="{base}/img/store.png" alt="app" height="200px" />
            </a>
            School Store
        </div>
        <!-- <div class="app">
            <a href="{base}/milestone">
                <img src="{base}/img/milestone.png" alt="app" height="200px" />
            </a>
            Milestone 7
        </div> -->
        <!-- <div class="app">
            <a href="/maintenance">
                <img src="/img/maintenance.png" alt="app" height="200px" />
            </a>
            Maintenance
        </div> -->
        <div class="app">
            <a rel="preload" href="{base}/tools">
                <img src="{base}/img/tools.png" alt="app" height="200px" />
            </a>
            Tool Check
        </div>
        <!-- <div class="app">
            <a href="/queue">
                <img src="/img/queue.png" alt="app" height="200px" />
            </a>
            Help Queue
        </div> -->
        <div class="app">
            <a rel="preload" href="{base}/docs">
                <img src="{base}/img/docs.png" alt="app" height="200px" />
            </a>
            Documentation
        </div>
        <div class="app">
            <a rel="preload" href="{base}/website">
                <img src="{base}/img/website.png" alt="app" height="200px" />
            </a>
            Website
        </div>
    </div>
</div>

<style>
    .apps {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-evenly;
    }
    .apps .app {
        text-align: center;
        display: flex;
        flex-direction: column;
        height: auto;
        margin: 0% 6%;
        margin-bottom: 3%;
    }
    @media (max-width: 900px) {
        .apps {
            width: 75%;
            height: 75%;
        }
        .apps .app {
            width: auto;
        }
    }

    @media (min-width: 900px) {
        .apps {
            width: 100%;
        }
        .apps .app {
            width: auto;
        }
    }
</style>
