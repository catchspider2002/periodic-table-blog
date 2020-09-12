<script>
  export let color, title, tags;
  let svgFile =
    "<svg width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(3) rotate(75)'><rect x='0' y='0' width='100%' height='100%' fill='hsla(" +
    color +
    ", 0.8)'/><g transform='translate(0,0)' stroke-width='0.5' stroke = 'none' fill='hsla(" +
    color +
    ", 1)'><path d='M0 40V20l20 20H0M40 0v20L20 0h20M20 20h20L20 40V20m0-20v20H0z'/></g></pattern></defs><rect width='100%' height='100%' fill='url(%23a)'/></svg>";
  $: cssOutput = 'background-image: url("data:image/svg+xml,' + svgFile + '")';
</script>

<style>
  .header {
    min-height: 80vh;
    padding: 1.5em;
    display: grid;
    place-items: center;
    background-color: black;
  }

  h1 {
    font-weight: 500;
    line-height: 1.1em;
    font-size: 2.8em;
    color: white;
  }

  .tags {
    display: grid;
    grid-gap: 0.75em;
    grid-auto-flow: column;
  }

  .tag {
    background-color: white;
    padding: 0.5em 0.75em;
    border-radius: var(--border-radius);
    font-size: 0.875em;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: hsl(var(--theme-color));
  }

  @media (max-width: 768px) {
    .header {
      place-items: start;
    }
  }
</style>

<section class="header" style={cssOutput}>
  <h1>{title}</h1>
  <div class="tags">
    {#each tags as { tag }}
      <a href="#a" class="tag">{tag}</a>
    {/each}
  </div>
</section>
