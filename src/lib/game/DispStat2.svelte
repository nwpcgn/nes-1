<script>
  import { _game } from "../../lib/data";
  import { addcomma } from "./utils";
  export let nr = false;
</script>

<span class="input-group-text" class:rounded-0={nr}>{addcomma($_game.msec)} /sec</span>

<style>
  span {
    background-color: transparent;
  }
</style>

