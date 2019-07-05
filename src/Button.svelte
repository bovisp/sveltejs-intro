<style>
  button {
    font: inherit;
    padding: .15rem .5rem;
    background-color: #d10057;
    border: 1px solid #d10057;
    color: #fff;
    cursor: pointer;
  }

  button:hover,
  button:active {
    box-shadow: 1px 1px 6px rgba(0, 0, 0, 0.26);
  }
</style>

<button on:click>
  <slot />
</button>