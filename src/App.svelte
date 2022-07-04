<script>
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  import FeedbackForm from "./components/FeedbackForm.svelte";

  $: averageFull =
    feedback.reduce((acc, { rating }) => acc + rating, 0) / feedback.length;
  $: average = averageFull.toFixed(2);
  $: count = feedback.length;

  const addFeedback = (event) => {
    const newFeedback = event.detail;
    feedback = [newFeedback, ...feedback];
  };

  const deleteFeebackItem = (event) => {
    console.log(event.detail);
    feedback = feedback.filter((item) => item.id !== event.detail);
  };
</script>

<main class="container">
  <FeedbackForm on:send-feedback={addFeedback} />
  <FeedbackStats {count} {average} />
  <FeedbackList on:delete-feedback-item={deleteFeebackItem} />
</main>

<style>
</style>
