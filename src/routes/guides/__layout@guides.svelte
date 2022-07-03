<script>
  import Title from '$lib/title.svelte';
  import '../../styles/global.css';
</script>

<header>
  <nav>
    <Title title="Learn Sveltekit" />
    <div class="links">
      <a href="/">Home</a>
      <a href="/about">About</a>
      <a href="/guides">Guides</a>
    </div>
  </nav>
</header>
<main>
  <slot />
</main>
<footer>
  <p>Copyright 2022 Learn SvelteKit Guides</p>
</footer>

<style>
  header {
    text-align: center;
    background: rgba(0, 0, 0, 0.1);
  }
  nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 0 20px;
  }
  main {
    max-width: 960px;
    margin: 20px auto;
  }
  footer {
    text-align: center;
  }
  .links {
    margin-left: auto;
  }
  a {
    margin-left: auto;
  }
</style>
