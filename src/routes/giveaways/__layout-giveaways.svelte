<script>
  import "../../styles/global.css";
</script>

<header>
  <nav>
    <div class="links">
      <a href="/">Home</a>
      <a href="/giveaways">Giveaways</a>
      <a href="/about">About</a>
      <div>
        <ul>
          <a href="/giveaways/platform/pc">PC</a>
          <a href="/giveaways/platform/steam">Steam</a>
          <a href="/giveaways/platform/epic-games-store">Epic Games Store</a>
          <a href="/giveaways/platform/itchio">itch.to</a>
          <a href="/giveaways/platform/gog">GOG</a>
          <a href="/giveaways/platform/ubisoft">Ubisoft</a>
          <a href="/giveaways/platform/battlenet">Battlenet</a>
          <a href="/giveaways/platform/origin">Origin</a>
          <a href="/giveaways/platform/xbox-one">Xbox One</a>
          <a href="/giveaways/platform/xbox-series-xs">Xbox Series X/S</a>
          <a href="/giveaways/platform/xbox-360">Xbox 360</a>
          <a href="/giveaways/platform/ps4">PS4</a>
          <a href="/giveaways/platform/ps5">PS5</a>
          <a href="/giveaways/platform/switch">Nitendo</a>
          <a href="/giveaways/platform/android">Android</a>
          <a href="/giveaways/platform/ios">iOS</a>
          <a href="/giveaways/platform/drm-free">DRM-Free</a>
          <a href="/giveaways">All Platforms</a>
        </ul>
      </div>
    </div>
  </nav>
</header>

<main class="giveaways">
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

  a {
    margin-left: 10px;
  }

  nav {
    display: flex;
    align-items: center;
    justify-content: center;
    max-width: 960px;
    margin: 0 auto;
  }
</style>
