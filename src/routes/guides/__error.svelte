<script context="module">
  export function load({ error, status }) {
    return {
      props: {
        message: error.message,
        status,
      },
    };
  }
</script>

<script>
  export let message;
  export let status;
</script>

<div class="error">
  <h2>Oops! The page was not found!</h2>
  <p>Error: {status} - {message}</p>
  <a href="/guides">View all guides</a>
</div>

<style>
  .error {
    text-align: center;
    margin-bottom: 60px;
  }
</style>
