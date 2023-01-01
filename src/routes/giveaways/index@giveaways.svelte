<script context="module">
  export async function load({fetch}) {
    const res = await fetch('https://www.gamerpower.com/api/giveaways', {
      headers: {"Access-control-allow-origin": "*"}
    });
    const giveaways = await res.json();

    if (res.ok) {
      return {
        props: {
          giveaways
        }
      };
    } else {
      return {
        status: res.status,
        error: new Error('Failed to fetch giveaways')
      };
    }
  }
</script>

<script>
  export let giveaways;
</script>

<div class="giveaways">
  <ul>
    {#each giveaways as giveaway}
      <li>
        <img width="280px" height="200px" src={giveaway.thumbnail} alt="thumbnail">
        <a sveltekit:prefetch href={`/giveaways/${giveaway.id}`}>{giveaway.title}</a>
      </li>
    {/each}
  </ul>
</div>

<style>
  .giveaways {
    margin-top: 20px;
  }
  ul {
    list-style: none;
    padding: 0;
  }
  a {
    display: inline-block;
    margin-top: 10px;
    margin-left: 10px;
    padding: 10px;
    border: 1px dotted rgba(255, 255, 255, 0.2);
  }

  li {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }
</style>
