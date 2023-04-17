<script>
  import SpaceBar from "../lib/components/SpaceBar.svelte";
  import Hero from "../lib/components/Hero.svelte";
  let step = 3;
  const updateCount = () => {
    if (step >= 8) {
      step = 0;
    } else {
      step++;
    }
  };
</script>

<section class="page flex">
  <div class="container-lg">
    <div class="grid async">
      <Hero bind:step>
        <footer>
          <button on:click={updateCount} type="button" class="nes-btn"
            >Step {step + 1}</button
          >
        </footer>
      </Hero>
      <aside class="aside">
       <!--  <div class="lists">
          <ul class="nes-list flex">
            <li><span>Prod</span><span>1</span></li>
            <li><span>Cats</span><span>1</span></li>
            <li><span>Wiz</span><span>1</span></li>
          </ul>
        </div> -->
        <button type="button" class="nes-btn xis-primary">Upgrades</button>
        <button type="button" class="nes-btn xis-error">Settings</button>
        <!--  <button type="button" class="nes-btn is-warning">Warning</button> -->
      </aside>
    </div>
  </div>
  <SpaceBar />
</section>

<style>
  footer {
    position: absolute;
    z-index: 100;
    bottom: 0;
    left: 0;
    padding: 0.25rem;
  }
</style>
