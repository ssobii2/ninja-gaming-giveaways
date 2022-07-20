<script context="module">
  export async function load({ fetch, params }) {
    const id = params.id;
    const res = await fetch(`https://www.gamerpower.com/api/giveaway?id=${id}`);
    const guide = await res.json();

    if (res.ok) {
      return {
        props: {
          guide,
        },
      };
    } else {
      return {
        status: 301,
        // error: new Error("Failed to fetch the guide"),
        redirect: "/guides",
      };
    }
  }
</script>

<script>
    export let guide;
</script>

<div class="guide">
    <h1>{guide.title}</h1>
    <h3>{guide.description}</h3>
    <h3>Instructions: {guide.instructions}</h3>
    <p>Worth: {guide.worth}</p>
    <p>Type: {guide.type}</p>
    <p>Platforms: {guide.platforms}</p>
    <p>End Date: {guide.end_date}</p>
    <p>Status: {guide.status}</p>
    <a href={guide.open_giveaway_url} target="_blank">Giveaway URL</a>
    <img src={guide.image} alt="guide">
</div>

<style>
  .guide {
    margin-top: 10px;
    padding: 10px;
    border: 1px dotted rgba(255, 255, 255, 0.2);
  }

  a {
    display: block;
    margin-bottom: 10px;
  }
</style>
