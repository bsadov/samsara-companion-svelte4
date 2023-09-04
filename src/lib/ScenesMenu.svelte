<script>
  import { seconds, storedcurrent, storedscenes, formatTime } from "./stores.js";

  function selectLocation(location) {
    $storedcurrent = location;
    $seconds = location.start;
  }

  function focusElement(ele) {
    ele.focus();
  }
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
<ul>
  {#each $storedscenes as scene}
    <li on:click={() => selectLocation(scene)}>
      {#if $storedcurrent == scene}
        <a href="#menu" use:focusElement>[{formatTime(scene.start)}] <b>{scene.name}</b></a>
      {:else}
        <a href="#menu">[{formatTime(scene.start)}] {scene.name}</a>
      {/if}
    </li>
  {/each}
</ul>

<style>
  ul {
    text-align: left;
    list-style: none;
  }

  li {
    cursor: pointer;
  }

  b {
    font-family: "Oregano";
    font-size: 1.2em;
    color: lightblue;
  }
</style>
