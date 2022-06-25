<script>
  import Button from "./Button.svelte";
  import Card from "./Card.svelte";
  import RatingSelector from "./RatingSelector.svelte";
  import { v4 as uuidv4 } from "uuid";

  let text = "";
  let btnDisable = true;
  let message = "";
  let rating = 10;

  const handleInput = () => {
    if (text.trim().length <= 10) {
      message = `Review must be longer than ten characters.`;
      btnDisable = true;
    } else {
      message = "";
      btnDisable = false;
    }
  };
  const handleSelect = (event) => {
    rating = event.detail;
  };
  const handleSubmit = () => {
    if (text.trim().length > 10) {
      const newFeedback = {
        id: uuidv4(),
        text,
        rating: +rating,
      };
      console.log(newFeedback);
    }
  };
</script>

<Card>
  <header>
    <h2>How would you rate us?</h2>
  </header>
  <form on:submit|preventDefault={handleSubmit}>
    <RatingSelector on:rating-select={handleSelect} />
    <div class="input-group">
      <input
        type="text"
        on:input={handleInput}
        bind:value={text}
        placeholder="Review Us!"
      />
      <Button disabled={btnDisable} type="submit">Submit</Button>
    </div>
    {#if message}
      <div class="message">{message}</div>
    {/if}
  </form>
</Card>

<style>
  header {
    max-width: 400px;
    margin: auto;
  }
  header h2 {
    font-size: 22px;
    font-weight: 600;
    text-align: center;
  }
  .input-group {
    display: flex;
    flex-direction: row;
    border: 1px solid #ccc;
    padding: 8px 10px;
    border-radius: 8px;
    margin-top: 15px;
  }
  input {
    flex-grow: 2;
    border: none;
    font-size: 16px;
  }
  input:focus {
    outline: none;
  }
  .message {
    padding-top: 10px;
    text-align: center;
    color: rebeccapurple;
  }
</style>
