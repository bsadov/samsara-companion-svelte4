<script>
  import { fade } from "svelte/transition";

  let visible = false;

  function expandMenu() {
    visible = !visible;
  }
</script>

<div id="shortcutMenu">
  <button id="shortcutButton" on:click={expandMenu}>Shortcuts</button>
  {#if visible}
    <div id="shortcutDisplay" transition:fade={{ duration: 300 }}>
      <ul>
        <li>M - Locations Menu</li>
        <li>P or Space - Play/Pause</li>
        <li>R - Reset</li>
        <li>Left Arrow - Previous Location</li>
        <li>Right Arrow - Next Location</li>
      </ul>
    </div>
  {/if}
</div>

<style>
  #shortcutMenu {
    text-align: right;
  }

  #shortcutButton {
    color: white;
    margin-top: 5px;
    background-color: rgb(62, 62, 62);
  }

  ul {
    list-style: none;
  }
</style>
