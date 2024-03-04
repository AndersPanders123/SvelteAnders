<!-- MyComponent.svelte -->

<script>
  let counter = 0;

  const increaseCounter = () => {
    counter += 10;
  };

  const decreaseCounter = () => {
    counter -= 10;
  };
</script>

<div class="row">
  <div class="button">
    <button on:click={increaseCounter}>+</button>
  </div>
  <div class="button">
    <button on:click={decreaseCounter}>-</button>
  </div>
</div>

<p>Tempratur: {counter}*C</p>

<style>
  /* Your styles for the component go here */
  .row {
    display: flex;
    flex-direction: row;
    /* Add any additional styling as needed */
  }

  .button {
    /* Styling for the button container */
    margin-right: 10px; /* Adjust as needed */
  }
</style>
