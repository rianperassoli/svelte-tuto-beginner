<script>
  let name = "Rian";
  let beltColour = "black";

  const handleClick = () => {
    beltColour = "orange";
  };

  const handleInput = (event) => {
    beltColour = event.target.value;
  };
</script>

<main>
  <h1>Hello {name}!</h1>
  <p style="color: {beltColour}">{beltColour} belt</p>

  <button on:click={handleClick}>update belt color</button>

  <!-- When need a two way data binding use the bind:value.  -->
  <!-- When need a one way data binding use value and or on:input.  -->

  <!-- <input type="text" on:input={handleInput} value={beltColour}/> -->
  <input type="text" bind:value={beltColour}/>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
