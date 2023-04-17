<script>
  import SpaceBar from "../lib/components/SpaceBar.svelte";
  import Hero from "../lib/components/Hero.svelte";
</script>

<section class="page flex">
  <div class="container-lg">
    <div class="grid async">
      <Hero />
      <aside class="aside">
        <button type="button" class="nes-btn is-primary">Primary</button>
        <button type="button" class="nes-btn is-success">Success</button>
        <button type="button" class="nes-btn is-error">Error</button>
        <!--  <button type="button" class="nes-btn is-warning">Warning</button> -->
      </aside>
    </div>
  </div>
  <SpaceBar />
</section>
