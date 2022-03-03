<script>
    import FeedbackList from './compoments/FeedbackList.svelte'
    import FeedbackStats from "./compoments/FeedbackStats.svelte";
    import FeedbackForm from "./compoments/FeedbackForm.svelte";
  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Many novice writers tend to make a sharp distinction between content and style, thinking that a paper can be strong in one and weak in the other, but focusing on organization shows how content and style converge in deliberative academic writing. Your professors will view even the most elegant prose as rambling and tedious if there isn’t a careful, coherent argument to give the text meaning. Paragraphs are the “stuff ” of academic writing and, thus, worth our attention here. ",
    },
    {
      id: 2,
      rating: 9,
      text: "Many novice writers tend to make a sharp distinction between content and style, thinking that a paper can be strong in one and weak in the other, but focusing on organization shows how content and style converge in deliberative academic writing. Your professors will view even the most elegant prose as rambling and tedious if there isn’t a careful, coherent argument to give the text meaning. Paragraphs are the “stuff ” of academic writing and, thus, worth our attention here. ",
    },
    {
      id: 3,
      rating: 8,
      text: "Many novice writers tend to make a sharp distinction between content and style, thinking that a paper can be strong in one and weak in the other, but focusing on organization shows how content and style converge in deliberative academic writing. Your professors will view even the most elegant prose as rambling and tedious if there isn’t a careful, coherent argument to give the text meaning. Paragraphs are the “stuff ” of academic writing and, thus, worth our attention here. ",
    },
  ]

    $: count = feedback.length
    $: average = feedback.reduce((a, {rating}) => a + rating , 0 ) / feedback.length
    const deleteFeedback = (e) => {
        const itemId = e.detail
        feedback = feedback.filter((item) => item.id != itemId)
    }
</script>

<main class="container">
    <FeedbackForm />
    <FeedbackStats {count} {average} />
    <FeedbackList {feedback} on:delete-feedback={deleteFeedback}/>
</main>
