<script>
  export let color, title, tags;
  let newtags = [];
  tags.forEach(letter => {
    newtags.push({ tag: letter });
  });

  import html2canvas from "html2canvas";
  import JavascriptSvg from "./JavascriptSVG.svelte";

  function screenshot() {
    console.log("screenshot");
    // html2canvas(document.getElementById("target1")).then(function(canvas) {
    html2canvas(document.body, {
      width: 1200,
      height: 627,
      y: 50
    }).then(function(canvas) {
      console.log("before append");
      document.body.appendChild(canvas);
    });
  }
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
  @media (max-width: 1440px) {
    :global(body) {
      font-size: 18px;
    }
  }
  @media (max-width: 768px) {
    :global(body) {
      font-size: 16px;
    }
  }
  @media (max-width: 400px) {
    :global(body) {
      font-size: 14px;
    }
  }
  .header {
    /* min-height: 630px; */
    padding: 2em;
    display: grid;
    grid-template-columns: 1fr;
    place-content: center;
    background-color: hsl(var(--theme-color));
  }

  h1 {
    font-family: "Montserrat", sans-serif;
    font-weight: 600;
    line-height: 1.2;
    /* letter-spacing: 0.05em;
    word-spacing: 0.25em; */
    font-size: 3.2em;
    color: var(--bg);
    padding: 0.5em 0.75em;
    margin: 0;
  }

  .tag {
    line-height: 0;
    padding: 0.25em 0.5em;
    border-radius: var(--border-radius);
    font-size: 1.6em;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    background-color: var(--bg);
    color: hsl(var(--theme-color));
    margin-bottom: 2em;
    margin-left: 1.75em;
  }

  @media (max-width: 768px) {
  }
</style>

-
<section class="header">
    <JavascriptSvg />
  <!-- <div class="leftSide">
    <span class="tag">JAVASCRIPT</span>
    <h1>{title}</h1>
  </div>
  <div class="rightSide">
  </div> -->

</section>

<button on:click={screenshot}>to image</button>
