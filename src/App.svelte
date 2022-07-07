<script>
  import FeedbackList from "./components/FeedbackList.svelte";
  import FeedbackStats from "./components/FeedbackStats.svelte";
  import FeedbackForm from "./components/FeedbackForm.svelte";

  // $: averageFull =
  //   feedback.reduce((acc, { rating }) => acc + rating, 0) / feedback.length;
  // $: average = averageFull.toFixed(2);
  // $: count = feedback.length;


  // Removed from <FeedbackForm on:send-feedback={addFeedback} />
  // const addFeedback = (event) => {
  //   const newFeedback = event.detail;
  //   feedback = [newFeedback, ...feedback];
  // };

  // Removed from <FeedbackList on:delete-feedback-item={deleteFeebackItem}/>
  //
  // const deleteFeebackItem = (event) => {
  //   console.log(event.detail);
  //   feedback = feedback.filter((item) => item.id !== event.detail);
  // };


</script>

<main class="container">
  <FeedbackForm />
  <FeedbackStats />
  <FeedbackList />
</main>

<style>
</style>
