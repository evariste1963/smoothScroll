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

  
</script>

<nav>
  <a href="/" use:scrollTo={{ ref: 'home', duration: 1000, easing: sineInOut }}
    >Home</a
  >
  <a href="/" use:scrollTo={{ ref: 'about', duration: 1500, easing: sineInOut }}
    >About</a
  >
  <a href="/" use:scrollTo={{ ref: 'blog', duration: 2000, easing: sineInOut }}
    >Blog</a
  >
</nav>
<section class="null" />
<section class="home" use:scrollRef={"home"}>
  <div>this is the home section</div>
  <button on:click={() => scrollTop()}>Go to top</button>
</section>
<section class="about" use:scrollRef={"about"}>
  <div>this is the about section</div>
  <button on:click={() => scrollTop()}>Go to top</button>
</section>
<section class="blog" use:scrollRef={"blog"}>
  <div>this is the blog section</div>
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
