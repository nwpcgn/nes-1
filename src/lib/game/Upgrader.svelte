<script>
  import { onMount } from "svelte";
  let ready = false;
  // console.log("INIT Upgrader");
  onMount(() => {
    // console.log("MOUNT Upgrader");
    ready = true;
  });
  import { _game } from "../../lib/data";
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

  const updateStore = () => {
    _game.set({
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
    });
  };
  function upgrade(name) {
    if (name === "kitten") {
      if (money >= catcost && catown < 50) {
        if (catown <= 13) {
          msec += catadd;
          catadd++;
          cboost = 1;
        } else if (catown == 14) {
          msec += catadd;
          catadd++;
          cboost = 200;
        } else if (catown <= 23) {
          msec += 200 * catadd;
          catadd++;
          cboost = 200;
        } else if (catown == 24) {
          msec += 200 * catadd;
          catadd++;
          cboost = 5000;
        } else if (catown <= 48) {
          msec += 5000 * catadd;
          catadd++;
          cboost = 5000;
        } else if (catown == 49) {
          msec += 5000 * catadd;
          catadd++;
          cboost = 15000;
        } else {
          msec += 15000 * catadd;
          catadd++;
          cboost = 15000;
        }
        catown += 1;
        money -= catcost;
        catcost = catcost * 2;
      }
    }
    if (name === "worker") {
      if (money >= workercost && workerown < 50) {
        if (workerown <= 13) {
          msec += workadd;
          workadd++;
          wboost = 1;
        } else if (workerown == 14) {
          msec += workadd;
          workadd++;
          wboost = 200;
        } else if (workerown <= 23) {
          msec += 200 * workadd;
          workadd++;
          wboost = 200;
        } else if (workerown == 24) {
          msec += 200 * workadd;
          workadd++;
          wboost = 5000;
        } else if (workerown <= 48) {
          msec += 5000 * workadd;
          workadd++;
          wboost = 5000;
        } else if (workerown == 49) {
          msec += 5000 * workadd;
          workadd++;
          wboost = 15000;
        } else {
          msec += 15000 * workadd;
          workadd++;
          wboost = 15000;
        }
        workerown += 1;
        money -= workercost;
        workercost = workercost * 3;
      }
    }

    if (name === "upgrade") {
      if (money >= upcost) {
        moneyup += upcost / 15;
        money -= upcost;
        upown += 1;
        upcost = upcost * 5;
        if (catown == 50) {
          msec -= catmax;
          catmax = Math.floor(moneyup * 0.15);
          msec += catmax;
        }
        if (workerown == 50) {
          msec -= workmax;
          workmax = Math.floor(moneyup * 0.35);
          msec += workmax;
        }
      }
    }

    updateStore()
  }

  // $: updateStore(money);
</script>

{#if ready}
  <slot {upgrade} />
{/if}
