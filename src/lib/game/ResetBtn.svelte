<script>
  import { _game } from "../../lib/data";
  import { resetValues } from "./utils";
  import Fa from "svelte-fa";
  import {
    faUndoAlt,
    faTimesCircle,
    faTimes,
  } from "@fortawesome/free-solid-svg-icons";
  const resetGame = () => {
    _game.set(resetValues);
  };
  let show = false;
  const clickReset = () => {
    show = false;
    resetGame();
  };
  const onClick = () => {
    show = !show;
  };
  export let nr = false;
</script>

<button
  on:click={onClick}
  class="btn {show ? 'btn-secondary' : 'btn-outline-secondary'}"
  class:rounded-0={nr}
  type="button"
  aria-label="Reset"
>
  <span class="visually-hidden">{show ? "Cancel" : "Reset"}</span>
  <Fa icon={show ? faTimes : faUndoAlt} fw />
</button>
{#if show}
  <button on:click={clickReset} class="btn btn-outline-danger" type="button"
    >Reset Game?</button
  >
{/if}

<style>
  button {
    transition: all 250ms;
  }
</style>
