<script>
  let firstName = "Richard";
  let lastName = "Miller Wimmer";
  let color = "blue";
  let showText = false;
  let users = [
    {
      id: 1,
      name: "John",
    },
    {
      id: 2,
      name: "Joe",
    },
    {
      id: 3,
      name: "Jane",
    },
  ];

  $: name = `${firstName} ${lastName}`;

  const toggleColor = () => {
    color = color === "blue" ? "purple" : "blue";
    showText = !showText;
    users = [...users, { id: 4, name: "James" }];
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
  {#each users as user (user.id)}
    <h3>{user.id}: {user.name}</h3>
  {/each}
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
