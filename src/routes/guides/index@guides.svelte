<script context="module">
  export async function load({fetch}) {
    await new Promise(resolve => setTimeout(resolve, 1000));
    const res = await fetch('https://www.gamerpower.com/api/giveaways');
    const guides = await res.json();

    if (res.ok) {
      return {
        props: {
          guides
        }
      };
    } else {
      return {
        status: res.status,
        error: new Error('Failed to fetch guides')
      };
    }
  }
</script>

<script>
  export let guides;
</script>

<div class="guides">
  <ul>
    {#each guides as guide}
      <li>
        <img width="280px" height="200px" src={guide.thumbnail} alt="thumbnail">
        <a sveltekit:prefetch href={`/guides/${guide.id}`}>{guide.title}</a>
      </li>
    {/each}
  </ul>
</div>

<style>
  .guides {
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
