<script>
  import "../../styles/global.css";
</script>

<header>
  <nav>
    <div class="links">
      <a href="/">Home</a>
      <a href="/guides">Guides</a>
      <a href="/about">About</a>
    </div>
  </nav>
</header>
<main class="guides">
  <slot />
</main>

<style>
  header {
    text-align: center;
  }

  main {
    max-width: 960px;
    margin: 20px auto;
  }

  .links {
    margin-left: auto;
  }

  a {
    margin-left: 10px;
  }

  nav {
    display: flex;
    align-items: center;
    max-width: 960px;
    margin: 0 auto;
  }
</style>
