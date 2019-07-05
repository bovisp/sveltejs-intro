<script>
  import { createEventDispatcher } from 'svelte'
  import Button from './Button.svelte'

  export let product

  const dispatch = createEventDispatcher()

  const addToCart = e => dispatch('cartadd', product.title)
</script>

<style>
  div {
    margin: 1rem;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1em;
    border-radius: 5px;
    background-color: #fff;
  }

  h1 {
    font-size: 1.25rem;
    margin: .25rem 0;
  }

  h2 {
    font-size: 1rem;
    margin: .25rem 0;
    color: #4b4b4b;
  }

  p {
    margin: .25rem 0;
  }
</style>

<div>
  <h1>
    {product.title}
  </h1>

  <h2>
    {product.price}
  </h2>

  <p>
    {product.description}
  </p>

  <Button on:click={addToCart}>
    Add to cart
  </Button>
</div>