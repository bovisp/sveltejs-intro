<script>
  import { createEventDispatcher } from 'svelte'
  import Product from './Product.svelte'
  
  export let products
 
  const dispatch = createEventDispatcher()

  const addToCart = e => dispatch('cartadd', e.detail)
</script>

{#if !products.length}
  <p>No products were added yet.</p>

  {:else}

  {#each products as product}
    <Product 
      product={product}
      on:cartadd={addToCart}
    />
  {/each}
{/if}