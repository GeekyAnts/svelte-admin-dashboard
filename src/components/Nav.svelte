<script>
  export let segment;
</script>

<style>
  nav {
    background: #24cea3;
    width: 270px;
    height: 100vh;
    position: fixed;
    left: 0;
    font-weight: 300;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: flex;
  }

  .selected {
    position: relative;
    display: inline-block;
    background: #1ea97f;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
    width: 100%;
    color: white;
  }
</style>

<nav>
  <ul>
    <li>
      <a class:selected={segment === undefined} href=".">home</a>
    </li>
    <li>
      <a class:selected={segment === 'about'} href="about">about</a>
    </li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li>
      <a rel="prefetch" class:selected={segment === 'blog'} href="blog">blog</a>
    </li>
  </ul>
</nav>
