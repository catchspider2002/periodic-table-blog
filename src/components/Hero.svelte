<script>
  export let color, title, tags;
  let svgFile =
    "<svg width='1200' height='627' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(3) rotate(75)'><rect x='0' y='0' width='100%' height='100%' fill='hsla(" +
    // "<svg width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(3) rotate(75)'><rect x='0' y='0' width='100%' height='100%' fill='hsla(" +
    color +
    ", 0.8)'/><g transform='translate(0,0)' stroke-width='0.5' stroke = 'none' fill='hsla(" +
    color +
    ", 1)'><path d='M0 40V20l20 20H0M40 0v20L20 0h20M20 20h20L20 40V20m0-20v20H0z'/></g></pattern></defs><rect width='100%' height='100%' fill='url(%23a)'/></svg>";
    

  $: cssOutput = 'background-image: url("data:image/svg+xml,' + svgFile + '")';
</script>

<style>
:root{
  --fg: black;
  --bg: white;
}

  .header {
    min-height: 80vh;
    padding: 1.5em;
    display: grid;
    place-items: center;
    background-color: var(--fg);
  }

  h1 {
  font-weight: 500;
line-height:1.4;
  font-size: 2.8em;
	color: hsl(var(--theme-color));
	padding: .5em 1em ;
  text-transform: uppercase;
  margin: 0;
  font-family: league-spartan;
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

  
.stripe {
/*     background-color: rgba(0,0,0,0.9); */
    padding: 1rem;
	margin: 2rem;
	border-radius: 1rem;
/* 	border: 4px solid red; */
    
    transform: rotate(-5deg) skew(-5deg);
}
.stripe__content {
/*     transform: skew(5deg); */
	background-color: rgba(255,255,255, 0.5);
}
	
.sample-heading-3 {
  font-size: 1em;
  padding: 1em;
  border-style: solid;
  border-width: 4px;
  border-image-source: url("data:image/svg+xml;charset=utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 40 40'><rect x='0.5' y='0.5' width='39' height='39' fill='transparent' stroke='white' stroke-width='2' /></svg>");
  border-image-slice: 50%;
  border-image-width: 48px;
	margin: 10px;
}
</style>

<section class="header" style={cssOutput}>
  <!-- <h1>{title}</h1> -->


<div class="stripe sample-heading-3">
    <div class="stripe__content">
			<h1>{title}</h1>
    </div>
</div>

  <div class="tags">
    {#each tags as { tag }}
      <a href="#a" class="tag">{tag}</a>
    {/each}
  </div>
</section>
