<script>
  import { FeedbackStore } from "../stores";

  $: averageFull =
    $FeedbackStore.reduce((acc, { rating }) => acc + rating, 0) /
    $FeedbackStore.length;
  $: average = averageFull.toFixed(2);
  $: count = $FeedbackStore.length;
</script>

<div class="feedback-stats">
  <h4>{count} Reviews</h4>
  <h4>Average Rating: {average}</h4>
</div>

<style>
  .feedback-stats {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
