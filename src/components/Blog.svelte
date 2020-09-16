<script>
  // let root = document.documentElement;
  let color = "234, 41%, 34%";
  // import PageProgress from "svelte-page-progress"
  import { onMount } from "svelte";

  import Hero from "./Hero.svelte";
  import html2canvas from "html2canvas";

  onMount(async () => {
    html2canvas(document.body).then(function(canvas) {
      // console.log("Added in onmount")
      // document.body.appendChild(canvas);
    });
  });

  // root.style.setProperty("--theme-color", color);
</script>

<style>
  :root {
    --theme-color: 234, 41%, 34%;
  }
</style>

<!-- <PageProgress color=hsl({color}) /> -->

<div class="body-text body-bg">
  <Hero {color} title="How to remove a specific item from an array?" tags={[{ tag: 'JAVASCRIPT' }, { tag: 'ES6' }]} />
  <section class="container">Since there is only a single return line, you can further simplify this as check</section>
</div>
