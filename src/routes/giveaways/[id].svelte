<script context="module">
  export async function load({ fetch, params }) {
    const id = params.id;
    const res = await fetch(`https://www.gamerpower.com/api/giveaway?id=${id}`);
    const giveaway = await res.json();

    if (res.ok) {
      return {
        props: {
          giveaway,
        },
      };
    } else {
      return {
        status: 301,
        error: new Error("Failed to fetch the giveaway"),
        // redirect: "/guides",
      };
    }
  }
</script>

<script>
  export let giveaway;
</script>

<div class="giveaway">
  <h1>{giveaway.title}</h1>
  <h3>{giveaway.description}</h3>
  <h3>Instructions: {giveaway.instructions}</h3>
  <p>Worth: {giveaway.worth}</p>
  <p>Type: {giveaway.type}</p>
  <p>Platforms: {giveaway.platforms}</p>
  <p>End Date: {giveaway.end_date}</p>
  <p>Status: {giveaway.status}</p>
  <a href={giveaway.open_giveaway_url} target="_blank">Giveaway URL</a>
  <img src={giveaway.image} alt="guide" />
</div>

<style>
  .giveaway {
    margin-top: 10px;
    padding: 10px;
    border: 1px dotted rgba(255, 255, 255, 0.2);
  }

  a {
    display: block;
    margin-bottom: 10px;
  }
</style>
