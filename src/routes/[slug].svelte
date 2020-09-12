<script context="module">
  export async function preload({ params, query }) {
    // the `slug` parameter is available because
    // this file is called [slug].svelte
    const res = await this.fetch(`${params.slug}.json`);
    const data = await res.json();

    if (res.status === 200) {
      return { post: data };
    } else {
      this.error(res.status, data.message);
    }
  }
</script>

<script>
  export let post;
  import NavBar from "../components/NavBar.svelte";
  import Blog from "../components/Blog.svelte";
</script>

<style>
  /*
		By default, CSS is locally scoped to the component,
		and any unused styles are dead-code-eliminated.
		In this page, Svelte can't know which elements are
		going to appear inside the {{{post.html}}} block,
		so we have to use the :global(...) modifier to target
		all elements inside .content
	*/
  .content :global(h2) {
    font-size: 1.4em;
    font-weight: 500;
  }

  .content :global(ul) {
    line-height: 1.5;
  }

  .content :global(li) {
    margin: 0 0 0.5em 0;
  }
</style>

<svelte:head>
  <title>{post.title}</title>
  <link rel="canonical" href="https://blog.periodic-table.io/{post.slug}" />
  <meta name="description" content={post.description} />
  <meta name="keywords" content={post.keywords} />

  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://blog.periodic-table.io/{post.slug}" />
  <meta property="og:title" content={post.title} />
  <meta property="og:description" content={post.description} />
  {#if post.thumb}
    <meta property="og:image" content={post.thumb} />
  {/if}

  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image" />
  <meta property="twitter:url" content="https://blog.periodic-table.io/{post.slug}" />
  <meta property="twitter:title" content={post.title} />
  <meta property="twitter:description" content={post.description} />
  {#if post.thumb}
    <meta property="twitter:image" content={post.thumb} />
  {/if}
</svelte:head>
<NavBar />

<Blog />

<h1>{post.title}</h1>

<div class="content">
  {@html post.html}
</div>
