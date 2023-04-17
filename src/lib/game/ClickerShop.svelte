<script>
  // import ClickerBar from "./ClickerBar.svelte";
  import Shop from "./Shop.svelte";
  import Upgrader from "./Upgrader.svelte";
  import { _user, _game, _count } from "../../lib/data";
  import Hero from "../../lib/Hero.svelte";
  import Page from "../../lib/Page.svelte";
  export let pageData;
  
</script>

<Page y={2} content>
  <svelte:fragment slot="hero">
    <Hero {...pageData} />
  </svelte:fragment>
  <Upgrader let:upgrade>
    <Shop on:upgrade={(e) => upgrade(e.detail)} />
  </Upgrader>
</Page>