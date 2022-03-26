<script>
  import FeedbackList from "./components/FeedbackList.svelte";

  let feedback = [
    { id: 1, rating: 10, text: "some rating text lorem ipsum" },
    { id: 2, rating: 9, text: "some rating text lorem ipsum" },
    { id: 3, rating: 7, text: "some rating text lorem ipsum" },
  ];
</script>

<main>
  <FeedbackList feedback={feedback} />
</main>

<style>
</style>
