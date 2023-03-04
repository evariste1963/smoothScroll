<script>
  import { scrollTo, scrollRef, scrollTop } from "svelte-scrolling";
  import {
    bounceInOut,
    cubicIn,
    cubicInOut,
    cubicOut,
    elasticInOut,
    sineInOut,
    linear,
  } from "svelte/easing";

  let scrollArr = ['home', 'about', 'blog']
  
</script>

<nav>
  <a href="/" use:scrollTo={{ ref: scrollArr[0], duration: 1000, easing: sineInOut }}
    >{scrollArr[0]}</a
  >
  <a href="/" use:scrollTo={{ ref: scrollArr[1], duration: 1500, easing: sineInOut }}
    >{scrollArr[1]}</a
  >
  <a href="/" use:scrollTo={{ ref: scrollArr[2], duration: 2000, easing: sineInOut }}
    >{scrollArr[2]}</a
  >
</nav>
<section class="null" />
<section class={scrollArr[0]} use:scrollRef={scrollArr[0]}>
  <div>this is the {scrollArr[0]} section</div>
  <button on:click={() => scrollTop()}>Go to top</button>
</section>
<section class={scrollArr[1]} use:scrollRef={scrollArr[1]}>
  <div>this is the {scrollArr[1]} section</div>
  <button on:click={() => scrollTop()}>Go to top</button>
</section>
<section class={scrollArr[2]} use:scrollRef={scrollArr[2]}>
  <div>this is the {scrollArr[2]} section</div>
  <button on:click={() => scrollTop()}>Go to top</button>
</section>

<button on:click={() => scrollTop()}>Go to top</button>

<style>
  .null,
  .home,
  .about,
  .blog {
    width: 100vw;
    height: 800px;
  }
</style>
