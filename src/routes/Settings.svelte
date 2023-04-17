<script>
  import Hero from "../lib/components/Hero.svelte";

  import TopBar from "../lib/components/TopBar.svelte";
</script>

<section class="page">
  <div class="grid async">
    <figure class="figure">
      <img src="https://pinegrow.com/placeholders/img16.jpg" class="img-hero" />
    </figure>
    <aside class="aside">
      <button type="button" class="nes-btn is-primary">Primary</button>

      <button type="button" class="nes-btn is-success">Success</button>

      <button type="button" class="nes-btn is-warning">Warning</button>

      <button type="button" class="nes-btn is-error">Error</button>
    </aside>
  </div>
  <div class="spacer-bar">
    <button>Click me!</button>
  </div>
  <div class="py-4">
    <div class="nes-field">
      <label for="name_field">Your name</label>
      <input type="text" id="name_field" class="nes-input" />
    </div>
    <div class="nes-field">
      <label for="textarea_field">Textarea</label>
      <textarea id="textarea_field" class="nes-textarea" />
    </div>
    <div class="nes-field">
      <label for="default_select">Select</label>
      <div class="nes-select">
        <select required="" id="default_select">
          <option value="" disabled="" selected="" hidden="">Select...</option>
          <option value="0">To be</option>
          <option value="1">Not to be</option>
        </select>
      </div>
    </div>
  </div>
</section>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
