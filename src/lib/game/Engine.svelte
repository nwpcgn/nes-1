<script>
  import { onMount } from "svelte";
  let ready = false;
  onMount(() => {
    ready = true;
  });

  import { _game, _count } from "../../lib/data";
  import { onInterval, resetValues } from "./utils";

  function myTimer() {
    $_game.money += $_game.msec;
    // if ($_game.msec != 0) $_count += 1;
  }
  function resetGame() {
    _game.set(resetValues);
    _count.set(0);
    // console.clear();
  }
  function startGame() {
    if ($_game.msec == 0) {
      $_game.msec = 1;
    }
  }

  onInterval(myTimer, 1000);
</script>

{#if ready}
  <slot {resetGame} />
{/if}


