<script context="module">
  // load() is a special sveltekit function to get data.
  export async function load(context) {
    // Can also destructure for {fetch}.
    const res = await context.fetch(
      'https://jsonplaceholder.typicode.com/posts'
    );
    const guides = await res.json();
    // context.fetch() contains ok and status for use.
    if (res.ok) {
      return {
        props: {
          guides,
        },
      };
    }
    return {
      status: res.status,
      error: new Error('Could not fetch the guides'),
    };
  }
</script>

<script>
  export let guides;
</script>

<div class="guides">
  <h2>Svelte Guides</h2>
  <ul>
    <li><a href="/guides/guide1">Guide 1</a></li>
    <li><a href="/guides/guide2">Guide 2</a></li>
    {#each guides as guide (guide.id)}
      <li>
        <a sveltekit:prefetch href={`/guides/${guide.id}`}>{guide.title}</a>
      </li>
    {/each}
  </ul>
</div>

<style>
  .guides {
    margin-top: 20px;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  a {
    display: inline-block;
    margin-top: 10px;
    padding: 10px;
  }
</style>
