<script>
  export let items

  $: total = items.reduce((sum, currentValue) => {
    return sum + currentValue.price
  }, 0)
</script>

<style>
  ul {
    list-style: none;
    margin: 1rem;
    padding: 0;
  }

  li {
    margin: .5rem 0;
    padding: 1em;
    border: 1px solid #ccc;
  }

  h1 {
    font-size: 1.5rem;
    margin: 1rem;
  }
</style>

<section>
  {#if !items.length}
    <p>No cart items</p>

    {:else}
    <ul>
      {#each items as item}
       <li>{item.title} - ${item.price}</li>
      {/each}
    </ul>
  {/if}

  <h1>Total price: ${total}</h1>
</section>
