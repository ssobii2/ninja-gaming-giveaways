<script>
  import Title from "../lib/title.svelte";
  import "../styles/global.css";
</script>

<header>
  <nav>
    <Title title="Ninja Gaming Giveaways" />
  </nav>
</header>
<main>
  <slot />
</main>
<footer>
  <p>Copyright 2022 Ninja Gaming Giveaways</p>
</footer>

<style>
  header {
    display: flex;
    justify-content: center;
  }

  main {
    max-width: 960px;
    margin: 20px auto;
  }

  footer {
    text-align: center;
    margin-top: 70px;
  }
</style>
