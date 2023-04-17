<script>
	import { addcomma } from './utils';
  import { createEventDispatcher } from 'svelte'
  const dispatch = createEventDispatcher()
  import ShopCard from "./ShopCard.svelte";
  import { _game, _count } from "../../lib/data";

  $: ({
    money,
    moneyup,
    msec,
    upcost,
    catcost,
    workercost,
    upown,
    catown,
    workerown,
    catadd,
    workadd,
    cboost,
    wboost,
    catmax,
    workmax,
  } = $_game);
  const view1 = [
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_0.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_1.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_2.png",
    "https://nwp-cgn.de/studio/upload/kat24/server/php/files/camp1_3.png",
  ];
  let component = ShopCard;
  $: name1 = `Upgrade ${upown + 1}`;
  $: level1 = `${upown} &#128435;`;
  $: price1 = `${addcomma(upcost)}`;
  $: effect1 = `${addcomma(moneyup += upcost / 15)} /click`;
  $: disabled1 = upcost <= money;
  $: name2 = `Upgrade ${catown + 1}`;
  $: level2 = `${catown} &#128435;`;
  $: price2 = `${addcomma(catcost)}`;
  $: effect2 = `${addcomma(catadd * cboost)} /sec`;
  $: disabled2 = catcost <= money;
  $: name3 = `Upgrade ${workerown + 1}`;
  $: level3 = `${workerown} &#128435;`;
  $: price3 = `${addcomma(workercost)}`;
  $: effect3 = `${addcomma(workadd * wboost)} /sec`;
  $: disabled3 = workercost <= money;
const handleUpgrade = (e) => {
  dispatch("upgrade", e.detail)
};
</script>

<svelte:component
  this={component}
  label="Products"
  ev="upgrade"
  bind:name={name1}
  bind:level={level1}
  bind:price={price1}
  bind:effect={effect1}
  bind:disabled={disabled1}
  on:click={handleUpgrade}
/>

<svelte:component
  this={component}
  label="Cats"
  ev="kitten"
  bind:name={name2}
  bind:level={level2}
  bind:price={price2}
  bind:effect={effect2}
  bind:disabled={disabled2}
  on:click={handleUpgrade}
/>

<svelte:component
  this={component}
  label="Wizards"
  ev="worker"
  bind:name={name3}
  bind:level={level3}
  bind:price={price3}
  bind:effect={effect3}
  bind:disabled={disabled3}
  on:click={handleUpgrade}
/>
