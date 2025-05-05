<script lang="ts">
    import { onMount } from "svelte";
    onMount(() => {
        let mission_type = document.getElementById("mission");
        let click = document.getElementById("randomize");
        if (click && click instanceof HTMLButtonElement) {
            click.onclick = () => {
                if (mission_type && mission_type instanceof HTMLSelectElement) {
                    let mission = mission_type.value;
                    switch (mission) {
                        case "fire":
                            let tops = ["A", "B", "C"];
                            let lit = [
                                "1",
                                "2",
                                "3",
                                "4",
                                "1 and 2",
                                "1 and 3",
                                "1 and 4",
                                "2 and 3",
                                "2 and 4",
                                "3 and 4",
                                "1, 2, and 3",
                                "1, 2, and 4",
                                "2, 3, and 4",
                                "All flames",
                            ];
                            let flames = Math.floor(Math.random() * 14);
                            let topography = Math.floor(Math.random() * 3);
                            let fire = document.getElementById("objectives");
                            if (fire && fire instanceof HTMLDivElement) {
                                fire.innerHTML = `<div>Flames lit: ${lit[flames]}<br>Topography: ${tops[topography]}</div> <img src="/enes100-velma/img/mission_diagram_fire.png" alt="fire mission diagram" width="125"> `;
                            }
                            break;
                        case "seed":
                            let plots = ["A", "B", "C", "D"];
                            let plot = Math.floor(Math.random() * 4);
                            let seed = document.getElementById("objectives");
                            if (seed && seed instanceof HTMLDivElement) {
                                seed.innerHTML = `<div>Plantable plot: ${plots[plot]}</div><img src="/enes100-velma/img/mission_diagram_seed.png" alt="seed mission diagram" width="125">`;
                            }
                            break;
                        case "materials":
                            let materials = ["Foam", "Plastic"];
                            let weights = ["Light", "Medium", "Heavy"];
                            let material = Math.floor(Math.random() * 2);
                            let weight = Math.floor(Math.random() * 3);
                            let mat = document.getElementById("objectives");
                            if (mat && mat instanceof HTMLDivElement) {
                                mat.innerHTML = `Material: ${materials[material]}<br>Weight: ${weights[weight]}`;
                            }
                            break;
                        case "crash":
                            let orientations = ["Short", "Long"];
                            let sides = ["Facing the OTV", "Facing the Obstacles"];
                            let orientation = Math.floor(Math.random() * 2);
                            let side = Math.floor(Math.random() * 2);
                            let crash = document.getElementById("objectives");
                            if (crash && crash instanceof HTMLDivElement) {
                                crash.innerHTML = `Side of box facing OTV: ${orientations[orientation]}<br>Abnormality: ${sides[side]}`;
                            }
                            break;
                        case "data":
                            let pucks = ["Magnetic", "Non-magnetic"];
                            let puck = Math.floor(Math.random() * 2);
                            let data = document.getElementById("objectives");
                            if (data && data instanceof HTMLDivElement) {
                                data.innerHTML = `Puck magnetism: ${pucks[puck]}`;
                            }
                            break;
                        case "water":
                            let levels = ["20mm", "30mm", "40mm"];
                            let pollutants = ["Yes", "No"];
                            let level = Math.floor(Math.random() * 3);
                            let polluted = Math.floor(Math.random() * 2);
                            let water = document.getElementById("objectives");
                            if (water && water instanceof HTMLDivElement) {
                                water.innerHTML = `Water level: ${levels[level]}<br>Pollutants Present: ${pollutants[polluted]}`;
                            }
                            break;
                    }
                } else {
                    console.error;
                }
            };
        } else {
            console.error;
        }
    });
</script>

<svelte:head>
    <title>Enes100 Website</title>
</svelte:head>

<div class="text">
    <div id="randomizer">
        <div class="selection">
            <label>
                Mission
                <select id="mission">
                    <option value="fire">Fire</option>
                    <option value="water">Water</option>
                    <option value="seed">Seed</option>
                    <option value="data">Data</option>
                    <option value="materials">Materials</option>
                    <option value="crash">Crash</option>
                </select>
            </label><br />
            <button id="randomize">Get Randomization</button>
        </div>
        <div id="objectives"></div>
    </div>
    <div class="frame">
        <iframe
            src="https://docs.google.com/forms/d/e/1FAIpQLSeVwOT2y2NuPcOcq-aXiXq6SDLItOMQHyXFLyQMzl2uNIvGQw/viewform?embedded=true"
            title="plonk"
            width="100%"
            height="100%"
            frameborder="0"
            marginheight="0"
            marginwidth="0">Loading…</iframe
        >
    </div>
</div>

<style>
    @media (max-width: 1000px) {
        .text {
            flex-direction: column;
        }
        #randomizer {
            width: 70%;
            margin: 5% auto;
            flex-direction: row;
        }
        .frame {
            width: 100%;
            height: 90%;
        }
        #objectives {
        width: 300px;
        padding: 5px 10px;
        line-height: normal;
        flex-direction: row;
    }
    }
    @media (min-width: 1001px) {
        .text {
            flex-direction: row;
        }
        #randomizer {
            width: 25%;
            margin: auto;
            flex-direction: column;
        }
        .frame {
            height: 100%;
            width: 70%;
        }
        #objectives {
        padding: 5px 10px;
        line-height: normal;
        margin: 5px;
        flex-direction: column;
    }
    }
    #objectives {
        border: 1px solid white;
        background-color: rgba(0, 0, 0, 0.2);
        display: flex;
        justify-content: space-between;
    }
    .text {
        overflow: hidden;
    }
    .frame {
        overflow: scroll;
    }
    #randomizer {
        background-color: rgba(255, 255, 255, 0.2);
        border: 2px solid white;
        padding: 20px;
        height: fit-content;
        line-height: 30px;
        display: flex;
        justify-content: space-around;
    }
</style>
