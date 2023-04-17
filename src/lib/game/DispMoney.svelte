<script>
  import { _game } from "../../lib/data";
  import { addcomma } from "./utils";
  export let nr = false;
</script>

<input
  type="text"
  class="form-control text-end"
  class:rounded-0={nr}
  placeholder={addcomma($_game.money)}
  value={addcomma($_game.money)}
  aria-label="Money"
  readonly
/>
<span class="input-group-text">&euro;</span>

<style>
  span {
    background-color: transparent;
  }
</style>
