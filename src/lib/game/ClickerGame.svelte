<script>
  // import ClickerBar from "./ClickerBar.svelte";
  import Clicker from "./Clicker.svelte";
  import { _user, _game, _count } from "../../lib/data";
  import Page from "../../lib/Page.svelte";
  export let pageData;
  const view1 = [
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_0.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_1.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_2.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_3.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp2_0.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp2_1.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp2_2.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp2_3.png",
  ];
  // $: console.log(page_num, paginNav, daten);
</script>
<!-- <Hero {...pageData} /> -->
<Page bg={view1[$_game.upown < view1.length ? $_game.upown : 7]}>
  <Clicker />
</Page>
