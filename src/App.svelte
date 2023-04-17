<script>
  import Start from "./routes/Start.svelte";
  import Game from "./routes/Game.svelte";
  import Settings from "./routes/Settings.svelte";
  import Upgrade from "./routes/Upgrade.svelte";
  import TopBar from "./lib/components/TopBar.svelte";
  import Router from 'svelte-spa-router';
  const routes = {
    '/upgrade': Upgrade,
    '/settings': Settings,
    '/game': Game,
    '*': Start,
  }
</script>

<svelte:head>
  <title>NWP-PAGE</title>
  <link href="https://fonts.cdnfonts.com/css/press-start-2p" rel="stylesheet" />
</svelte:head>

<TopBar />

<main class="main">
  <Router {routes} />
</main>
