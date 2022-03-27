<script>
  import FeedbackList from "./components/FeedbackList.svelte";

  let feedback = [
    { id: 1, rating: 10, text: "some rating text lorem ipsum" },
    { id: 2, rating: 9, text: "some rating text lorem ipsum" },
    { id: 3, rating: 7, text: "some rating text lorem ipsum" },
  ];

  const deleteFeebackItem = (event) => {
    console.log(event.detail);
  };
</script>

<main class="container">
  <FeedbackList {feedback} on:delete-feedback-item={deleteFeebackItem} />
</main>

<style>
</style>
