<script context="module">
  export const load = async ({ fetch }) => {
    const res = await fetch("/graphql", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        query: `query { 
        books {
          title
          author
        }
      }`,
      }),
    });

    const { data } = await res.json();

    return {
      props: { data },
    };
  };
</script>

<script>
  export let data;
</script>

{JSON.stringify(data)}
<h1>Welcome to SvelteKit</h1>
<p>
  Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation
</p>
