<script>
  export let color, title, tags;
  let svgFile =
    "<svg width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(3) rotate(75)'><rect x='0' y='0' width='100%' height='100%' fill='hsla(" +
    color +
    ", 0.8)'/><g transform='translate(0,0)' stroke-width='0.5' stroke = 'none' fill='hsla(" +
    color +
    ", 1)'><path d='M0 40V20l20 20H0M40 0v20L20 0h20M20 20h20L20 40V20m0-20v20H0z'/></g></pattern></defs><rect width='100%' height='100%' fill='url(%23a)'/></svg>";

let newSvg = `
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" height="100" width="191">
  <defs>
    <path id="f" d="M274.049 150.448h197.849v82.358H274.049z"/>
    <path id="d" d="M266.16 148.87h207.316v85.829H266.16z"/>
  </defs>
  <defs>
    <path id="a" d="M0 45.766h750v500H0z"/>
  </defs>
  <clipPath id="b">
    <use height="100%" width="100%" overflow="visible" xlink:href="#a"/>
  </clipPath>
  <g transform="translate(-90.131 -44.052) scale(.4972)" clip-path="url(#b)" fill="#cffade" stroke-width="2.011">
    <defs>
      <path id="c" d="M0 45.766h750v500H0z"/>
    </defs>
    <clipPath id="e">
      <use height="100%" width="100%" overflow="visible" xlink:href="#c"/>
    </clipPath>
    <path d="M420.572 257.887a50.653 50.653 0 012.648-1.351c.75-.351 1.432-.646 2.128-.906a25.885 25.885 0 012.199-.709 46.9 46.9 0 012.891-.704c.13 1.247-.336 2.345-1.017 3.23a6.1 6.1 0 01-2.68 1.931 6.143 6.143 0 01-3.29.284c-1.092-.226-2.16-.752-2.879-1.775M191.371 140.499c.213 2.26.115 4.388-.039 6.49a78.135 78.135 0 01-.758 6.208 76.022 76.022 0 01-1.245 6.127c-.52 2.043-1.104 4.09-2.028 6.167-.74-2.15-1.013-4.323-1.1-6.488a32.999 32.999 0 01.425-6.449c.35-2.126.893-4.22 1.648-6.25.77-2.026 1.717-3.999 3.097-5.805m265.753-1.16c3.418-.507 7.04.416 10.147 2.12 3.125 1.726 5.806 4.19 7.855 7.151 2.078 2.99 3.269 6.596 3.484 10.13.22 3.549-.38 7.007-1.634 10.195-.395-3.408-.704-6.674-1.476-9.725-.75-3.053-1.958-5.845-3.672-8.339a32.698 32.698 0 00-6.287-6.798 28.4 28.4 0 00-8.417-4.733M263.078 90.38c-8.522-1.44-17.292-2.746-25.05-2.139-16.377 1.283-23.884 10.502-28.712 19.361-9.665 17.737-14.81 36.974-15.264 57.074-.178 7.893.394 16.029 4.457 24.337 4.063 8.309 11.954 16.886 23.855 23.269 11.462 6.147 25.459 9.722 38.965 13.112l82.297 20.657c22.857 5.737 47.839 11.613 67.414 8.234 16.114-2.781 25.137-11.33 32.445-19.858 16.113-18.804 27.956-39.805 26.988-63.42-.268-6.58-1.721-13.659-8.27-20.22-8.889-8.904-25.144-14.96-40.497-19.825-50.89-16.128-106.108-31.71-158.628-40.583" transform="rotate(-14.15 414.822 1.235)" clip-path="url(#e)" fill="#08491f"/>
    <text transform="translate(-.356 2.852)" x="109.053" style="line-height:125%;-inkscape-font-specification:'Noto Sans Hebrew';text-align:center;white-space:pre;shape-inside:url(#f)" font-size="20.113" font-family="Noto Sans Hebrew" letter-spacing="1.006" word-spacing="0" fill="none" stroke="#000">
      <tspan x="289.467" y="168.758"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">CONVERT TEXT </tspan></tspan><tspan x="297.029" y="194.608"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">TO STRING IN </tspan></tspan><tspan x="305.557" y="220.459"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">JAVASCRIPT</tspan></tspan>
    </text>
  </g>
</svg>`
    

  $: cssOutput = 'background-image: url("data:image/svg+xml,' + newSvg + '")';
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

  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" height="100" width="191">
  <defs>
    <path id="f" d="M274.049 150.448h197.849v82.358H274.049z"/>
    <path id="d" d="M266.16 148.87h207.316v85.829H266.16z"/>
  </defs>
  <defs>
    <path id="a" d="M0 45.766h750v500H0z"/>
  </defs>
  <clipPath id="b">
    <use height="100%" width="100%" overflow="visible" xlink:href="#a"/>
  </clipPath>
  <g transform="translate(-90.131 -44.052) scale(.4972)" clip-path="url(#b)" fill="#cffade" stroke-width="2.011">
    <defs>
      <path id="c" d="M0 45.766h750v500H0z"/>
    </defs>
    <clipPath id="e">
      <use height="100%" width="100%" overflow="visible" xlink:href="#c"/>
    </clipPath>
    <path d="M420.572 257.887a50.653 50.653 0 012.648-1.351c.75-.351 1.432-.646 2.128-.906a25.885 25.885 0 012.199-.709 46.9 46.9 0 012.891-.704c.13 1.247-.336 2.345-1.017 3.23a6.1 6.1 0 01-2.68 1.931 6.143 6.143 0 01-3.29.284c-1.092-.226-2.16-.752-2.879-1.775M191.371 140.499c.213 2.26.115 4.388-.039 6.49a78.135 78.135 0 01-.758 6.208 76.022 76.022 0 01-1.245 6.127c-.52 2.043-1.104 4.09-2.028 6.167-.74-2.15-1.013-4.323-1.1-6.488a32.999 32.999 0 01.425-6.449c.35-2.126.893-4.22 1.648-6.25.77-2.026 1.717-3.999 3.097-5.805m265.753-1.16c3.418-.507 7.04.416 10.147 2.12 3.125 1.726 5.806 4.19 7.855 7.151 2.078 2.99 3.269 6.596 3.484 10.13.22 3.549-.38 7.007-1.634 10.195-.395-3.408-.704-6.674-1.476-9.725-.75-3.053-1.958-5.845-3.672-8.339a32.698 32.698 0 00-6.287-6.798 28.4 28.4 0 00-8.417-4.733M263.078 90.38c-8.522-1.44-17.292-2.746-25.05-2.139-16.377 1.283-23.884 10.502-28.712 19.361-9.665 17.737-14.81 36.974-15.264 57.074-.178 7.893.394 16.029 4.457 24.337 4.063 8.309 11.954 16.886 23.855 23.269 11.462 6.147 25.459 9.722 38.965 13.112l82.297 20.657c22.857 5.737 47.839 11.613 67.414 8.234 16.114-2.781 25.137-11.33 32.445-19.858 16.113-18.804 27.956-39.805 26.988-63.42-.268-6.58-1.721-13.659-8.27-20.22-8.889-8.904-25.144-14.96-40.497-19.825-50.89-16.128-106.108-31.71-158.628-40.583" transform="rotate(-14.15 414.822 1.235)" clip-path="url(#e)" fill="#08491f"/>
    <text transform="translate(-.356 2.852)" x="109.053" style="line-height:125%;-inkscape-font-specification:'Noto Sans Hebrew';text-align:center;white-space:pre;shape-inside:url(#f)" font-size="20.113" font-family="Noto Sans Hebrew" letter-spacing="1.006" word-spacing="0" fill="none" stroke="#000">
      <tspan x="289.467" y="168.758"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">CONVERT TEXT </tspan></tspan><tspan x="297.029" y="194.608"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">TO STRING IN </tspan></tspan><tspan x="305.557" y="220.459"><tspan style="-inkscape-font-specification:'League Spartan Bold';text-align:center" font-weight="700" font-family="League Spartan" text-anchor="middle" fill="#3eb267" stroke="none">JAVASCRIPT</tspan></tspan>
    </text>
  </g>
</svg>

  <div class="tags">
    {#each tags as { tag }}
      <a href="#a" class="tag">{tag}</a>
    {/each}
  </div>
</section>
