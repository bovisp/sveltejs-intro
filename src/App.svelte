<script>
  import Button from './Button.svelte'
  import Products from './Products.svelte' 
  import Cart from './Cart.svelte'

  let title = ''
  let description = ''
  let price = 0
  let products = []
  let cart = []

  const create = e => products = products.concat({ title, description, price })

  const addToCart = e => cart = cart.concat({...products.find(item => e.detail === item.title)})
</script>

<style>
  input,
  textarea {
    width: 100%;
  }
</style>

<section>
  <div>
    <label for="title">Title</label>
    <input type="text" id="title" bind:value={title} />
  </div>

  <div>
    <label for="price">Price</label>
    <input type="number" id="price" bind:value={price} />
  </div>

  <div>
    <label for="description">Description</label>
    <textarea rows="3" id="description" bind:value={description} />
  </div>

  <div>
    <Button on:click={create}>Add product</Button>
  </div>
</section>

<section>
  <Products 
    products={products}
    on:cartadd={addToCart}
  />
</section>


<Cart 
  items={cart}
/>
