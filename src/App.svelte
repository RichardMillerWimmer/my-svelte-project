<script>
  let firstName = "Richard";
  let lastName = "Miller Wimmer";
  let color = "blue";
  let showText = false;

  $: name = `${firstName} ${lastName}`;

  const toggleColor = () => {
    color = color === "blue" ? "purple" : "blue";
    showText = !showText;
  };
</script>

<main>
  <h1 style="color: {color}">Hello, {name}!</h1>
  {#if showText}
    <p>
      Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
      how to build Svelte apps.
    </p>
  {:else}
    <p>showText is false and this it the : else</p>
  {/if}
  <button on:click={toggleColor}>color change</button>
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
