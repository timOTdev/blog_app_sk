<script>
  import Title from '$lib/title.svelte';

  let title = 'My Sveltekit Page';

  const updateTitle = () => {
    title = 'My Awesome Sveltekit Page';
  };
</script>

<Title />
<div class="index">
  <h2>{title}</h2>
  <p>
    Building an app with all the modern best practices is fiendishly
    complicated. Those practices include build optimizations, so that you load
    only the minimal required code; offline support; prefetching pages before
    the user initiates navigation; and configurable rendering that allows you to
    generate HTML on the server or in the browser at runtime or at build-time.
    SvelteKit does all the boring stuff for you so that you can get on with the
    creative part
  </p>

  <button on:click={updateTitle}>Update Title</button>
  <input type="text" bind:value={title} />

  <li><a href="/about">About</a></li>
  <li><a href="/guides">Guides</a></li>
</div>

<style>
  .index {
    text-align: center;
    display: block;
    margin: 20px auto;
  }
</style>
