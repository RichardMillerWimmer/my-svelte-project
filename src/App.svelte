<script>
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  import FeebackForm from "./components/FeedbackForm.svelte";
  import FeedbackForm from "./components/FeedbackForm.svelte";

  let feedback = [
    { id: 1, rating: 10, text: "some rating text lorem ipsum" },
    { id: 2, rating: 9, text: "some rating text lorem ipsum" },
    { id: 3, rating: 7, text: "some rating text lorem ipsum" },
  ];

  $: averageFull =
    feedback.reduce((acc, { rating }) => acc + rating, 0) / feedback.length;
  $: average = averageFull.toFixed(2);
  $: count = feedback.length;

  const deleteFeebackItem = (event) => {
    console.log(event.detail);
    feedback = feedback.filter((item) => item.id !== event.detail);
  };
</script>

<main class="container">
  <FeedbackForm />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:delete-feedback-item={deleteFeebackItem} />
</main>

<style>
</style>
