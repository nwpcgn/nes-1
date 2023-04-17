<script>
  import DispStat2 from "./DispStat2.svelte";
  import DispStat1 from "./DispStat1.svelte";
  import DispMoney from "./DispMoney.svelte";
  import ResetBtn from "./ResetBtn.svelte";
  export let stat = false;
  export let flex = false;
  export let reset = false;
  export let nr = false;
</script>

<div {...$$restProps}>
  <div class={flex ? 'd-flex' : 'input-group'}>
    {#if $$slots.start}
      <slot name="start"><!-- optional fallback --></slot>
    {/if}
    {#if reset}
    <ResetBtn {nr} />
    {/if}
    <DispMoney {nr} />
    {#if stat}
      <DispStat1 {nr} />
      <DispStat2 {nr} />
    {/if}
    {#if $$slots.end}
      <slot name="end"><!-- optional fallback --></slot>
    {/if}
  </div>
</div>

