<script>
  import SceneInfo from "../lib/SceneInfo.svelte";
  import TimerMenu from "../lib/TimerMenu.svelte";
  import ShortcutMenu from "../lib/ShortcutMenu.svelte";
  import "../app.css";

  let handleTimerKeydown;
  let handleShortcutKeydown;

  function passKeydown(event) {
    if (event.keyCode === 83) handleShortcutKeydown();
    else {
      handleTimerKeydown(event);
    }
  }
</script>

<h1 class="title">Samsara Companion</h1>
<TimerMenu bind:handleKeydown={handleTimerKeydown} />
<SceneInfo />
<ShortcutMenu bind:handleKeydown={handleShortcutKeydown} />

<footer>
  <p>@<a href="https://twitter.com/bsadov" alt="link to twitter page" target="_blank">bsadov</a>&nbsp;2023</p>
</footer>

<svelte:window on:keydown={passKeydown} />
