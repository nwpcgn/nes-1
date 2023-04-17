<script>
  import Bg2 from "./Bg2.svelte";
  import { Canvas } from "svelte-canvas";
  const bgs = [
    [
      "./img/s2/1/1.jpg",
      "./img/s2/1/2.jpg",
      "./img/s2/1/3.jpg",
      "./img/s2/1/4.jpg",
      "./img/s2/1/5.jpg",
      "./img/s2/1/6.jpg",
      "./img/s2/1/7.jpg",
      "./img/s2/1/8.jpg",
    ],
    [
      "./img/s2/2/1.jpg",
      "./img/s2/2/2.jpg",
      "./img/s2/2/3.jpg",
      "./img/s2/2/4.jpg",
      "./img/s2/2/5.jpg",
      "./img/s2/2/6.jpg",
      "./img/s2/2/7.jpg",
      "./img/s2/2/8.jpg",
    ],
    [
      "./img/s1/1/1.jpg",
      "./img/s1/1/2.jpg",
      "./img/s1/1/3.jpg",
      "./img/s1/1/4.jpg",
      "./img/s1/1/5.jpg",
      "./img/s1/1/6.jpg",
      "./img/s1/1/7.jpg",
      "./img/s1/1/8.jpg",
    ],
    [
      "./img/s1/2/1.jpg",
      "./img/s1/2/2.jpg",
      "./img/s1/2/3.jpg",
      "./img/s1/2/4.jpg",
      "./img/s1/2/5.jpg",
      "./img/s1/2/6.jpg",
      "./img/s1/2/7.jpg",
      "./img/s1/2/8.jpg",
    ],
  ];
  export let left = false;
  export let step = 5;
  let max = bgs.length;
  let count = 0;
  $: width = 0;
  $: height = 0;
  const updateCount = () => {
    if (count + 1 >= max) {
      count = 0;
    } else {
      count++;
    }
  };
</script>

<section
  class="nes-pointer {left ? 'left' : 'right'}"
  bind:clientWidth={width}
  bind:clientHeight={height}
  on:click={updateCount}
>
  <Canvas {width} {height}>
    <Bg2 set={count} {step} {bgs} />
  </Canvas>
</section>

<style>
  section {
    position: absolute;
    overflow: hidden;
    width: 100%;
    z-index: 11;
    aspect-ratio: 16 / 9;
    top: 0;
    max-width: 33%;
    z-index: 16;
    border: 1px solid var(--bs-border-color);
  }
  section.right {
    right: 0;
  }
  section.left {
    left: 0;
  }
</style>
