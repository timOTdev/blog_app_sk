<script context="module">
  export async function load({ params, fetch }) {
    const id = params.id;
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
    const guide = await res.json();

    if (res.ok) {
      return {
        props: {
          guide,
        },
      };
    }

    return {
      // If you want to redirect after any errors.
      // status: 301,
      // redirect: '/guides',

      // If we want to error instead of redirect. This sends out a custom message also.
      // The default error page: .svelte-kit/runtime/components/error.svelte
      status: res.status,
      error: new Error('Could not fetch that guide'),
    };
  }
</script>

<script>
  export let guide;
</script>

<div class="guide">
  <h2>{guide.title}</h2>
  <p>{guide.body}</p>
</div>

<style>
  .guide {
    margin-top: 40px;
    padding: 10px;
    border: 1px dotted rgba(255, 255, 255, 0.2);
  }
</style>
