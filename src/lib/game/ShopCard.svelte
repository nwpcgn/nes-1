<script>
  import { createEventDispatcher } from 'svelte'
  const dispatch = createEventDispatcher()
  export let label = "Products";
  export let name = "Upgrade";
  export let level = "&#128435;";
  export let price = "$";
  export let effect = "";
  export let disabled;
  export let ev = "Event";
  const onClick = () => {
    dispatch("click", ev)
  };
</script>

<div>
  <div class="d-flex w-100 justify-content-between">
    <h5 class="mb-2">{label}</h5>
    <span class="fs-6">{@html level}</span>
  </div>
  <div class="d-flex w-100 justify-content-between">
    <h6 class="mb-1">{name}</h6>
    <span class="text-muted">
      <span>{@html price} &euro;</span>
    </span>
  </div>
  <div class="d-flex w-100 justify-content-between">
    <span class="mb-1">Effect</span>
    <span class="text-muted">
      <span>{@html effect}</span>
    </span>
  </div>
  <div class="py-2">
    <button on:click={onClick} type="button" class="btn btn-primary btn-sm" disabled={!disabled}>Upgrade</button>
  </div>
</div>

