<script>
  export let aligner = false;
  export let y = 2;
  export let x = 0;
</script>

{#if $$slots.header}
  <header class="sticky-top shadow">
    <slot name="header" />
  </header>
{/if}

<main style="--y: {y}rem; --x: {x}rem">
  {#if aligner}
    <article>
      <slot />
    </article>
  {:else}
    <slot />
  {/if}
</main>
{#if $$slots.footer}
  <footer>
    <slot name="footerr" />
  </footer>
{/if}

<style>
  main {
    position: relative;
    flex: 1;
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    overflow-x: hidden;
    padding: var(--y) var(--x);
  }
  article {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
</style>
