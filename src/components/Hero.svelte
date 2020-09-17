<script>
  export let color, title, tags;
  let svgFile =
    "<svg width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(3) rotate(75)'><rect x='0' y='0' width='100%' height='100%' fill='hsla(" +
    color +
    ", 0.8)'/><g transform='translate(0,0)' stroke-width='0.5' stroke = 'none' fill='hsla(" +
    color +
    ", 1)'><path d='M0 40V20l20 20H0M40 0v20L20 0h20M20 20h20L20 40V20m0-20v20H0z'/></g></pattern></defs><rect width='100%' height='100%' fill='url(%23a)'/></svg>";
  let newtags = [];
  tags.forEach(letter => {
    newtags.push({ tag: letter });
  });
  $: cssOutput = 'background-image: url("data:image/svg+xml,' + svgFile + '")';
</script>

<style>
  :root {
    --bg: black;
    --fg: white;
    /* 		--bg: white;
		--fg: black; */
  }
  :global(body) {
    font-size: 20px;
  }
  .header {
    /* min-height: 100vh; */
    padding: 2.6em;
    display: grid;
    place-content: center;
    background-color: var(--fg);
  }

  h1 {
    /* font-family: "league-spartan"; */
    font-weight: 500;
    line-height: 1.4;
    letter-spacing: 0.05em;
    word-spacing: 0.25em;
    font-size: 2.8em;
    color: hsl(var(--theme-color));
    padding: 0.5em 1em;
    text-transform: uppercase;
    margin: 0;
  }

  .tags {
    display: grid;
    grid-gap: 1em;
    grid-auto-flow: column;
    place-content: end;
    margin: 0 1em;
  }

  .tag {
    background-color: hsl(var(--theme-color));
    padding: 0.5em 0.75em;
    margin-bottom: 1em;
    border-radius: var(--border-radius);
    font-size: 1em;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--bg);
  }
  .stripe {
    /* background-color: rgba(0,0,0,0.9); */
    border-radius: 1rem;
    transform: rotate(-5deg) skew(-5deg);
    font-size: 1em;
    padding: 1em;
    margin: 8em 0;
    border-style: solid;
    border-width: 4px;
    border-image-source: url("data:image/svg+xml;charset=utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 40 40'><rect x='0.5' y='0.5' width='39' height='39' rx='3' fill='transparent' stroke='black' stroke-width='2' /></svg>");
    border-image-slice: 50%;
    border-image-width: 48px;
  }

  .stripeHeader {
    border-radius: var(--border-radius);
    background-color: var(--bg);
    max-width: 1300px;
  }
  @media (max-width: 1440px) {
    :global(body) {
      font-size: 18px;
    }
    .stripe {
      margin: 6em 0;
    }
    .stripeHeader {
      max-width: 768px;
    }
  }
  @media (max-width: 768px) {
    :global(body) {
      font-size: 16px;
    }
    .header {
      place-items: start;
    }
    .stripe {
      margin: 4em 0;
    }
  }
  @media (max-width: 400px) {
    :global(body) {
      font-size: 14px;
    }
    .stripe {
      margin: 2em 0;
    }
  }
</style>

<section id="target" class="header" style={cssOutput}>
  <div class="stripe">
    <div class="stripeHeader">
      <h1 class="leagueSpartan">{title}</h1>
      <div class="tags">
        {#each newtags as { tag }}
          <a href="#a" class="tag">{tag}</a>
        {/each}
      </div>
    </div>
  </div>
</section>
