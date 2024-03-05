<script>
  import ovn from "../../src/ovn.png";
  import ovn2 from "../../src/ovn2.png";

  let counter = 0;
  let img = ovn;

  const increaseCounter = () => {
    counter += 10;
    onChange();
  };

  const decreaseCounter = () => {
    if (counter === 0) return;
    counter -= 10;
    onChange();
  };

  function onChange() {
    if (counter >= 210) img = ovn2;
    else img = ovn;
  }
</script>

<svelte:head>
  <style>
    @import url("https://fonts.googleapis.com/css2?family=Pixelify+Sans&display=swap");
  </style>
</svelte:head>

<div class="row">
  <div>
    <button class="button" on:click={increaseCounter}>+</button>
  </div>
  <div>
    <button class="button" on:click={decreaseCounter}>-</button>
  </div>
</div>
<p class="temp">
  Temperatur: {counter}°C
</p>

<div class="bilde">
  <div class="img">
    <img src={img} alt="Oven" />
  </div>
</div>

<style>
  @font-face {
    font-family: "Pixelify Sans";
    src: url("../../src/PixelifySans.ttf");
  }
  * {
    margin: 0;
    font-family: "pixel", sans-serif;
  }
  .row {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }

  .button {
    background-color: #04aa6d; /* Green */
    border: none;
    color: white;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 20px;
    border-radius: 15px;
    width: 55px;
  }
  .button:hover {
    border: black 1px solid;
    color: black;
  }

  .temp {
    font-family: "Pixelify Sans";
    text-align: center;
    font-size: 28px;
    margin-top: 10px;
    margin-bottom: 30px;
  }

  :global(body) {
    background-color: thistle;
  }

  .bilde {
    justify-content: center;
    display: flex;
  }
  .bilde img {
    width: 400px;
  }
</style>
