<script>
  import { createEventDispatcher } from "svelte";

  let dispatcher = createEventDispatcher();

  let binder = { question: "", answerA: "", answerB: "" };
  let error = { question: "", answerA: "", answerB: "" };
  let valid = false;

  const formSubmit = () => {
    valid = true; // Reset valid state before validation

    // Validate question (at least 5 words)
    if (binder.question.trim().split(/\s+/).length < 4) {
      valid = false;
      error.question = "Should have at least five words";
    } else {
      error.question = "";
    }

    // Validate answer A (not empty)
    if (binder.answerA.trim().length < 1) {
      valid = false;
      error.answerA = "Cannot be empty";
    } else {
      error.answerA = "";
    }

    // Validate answer B (not empty)
    if (binder.answerB.trim().length < 1) {
      valid = false;
      error.answerB = "Cannot be empty";
    } else {
      error.answerB = "";
    }

    if (valid) {
      let pollVote = {...fields, votesA, votesB, id: Math.random()}

      dispatcher('add', pollVote);
      // Reset form (optional)
      binder = { question: "", answerA: "", answerB: "" };
    }
  };
</script>

<form on:submit|preventDefault={formSubmit}>
  <div class="input-form">
    <label for="head-questions">Question</label>
    <input type="text" id="questions" bind:value={binder.question} />
    <div class="error">{error.question}</div>
  </div>

  <div class="input-form">
    <label for="answer-A">Answer A</label>
    <input type="text" id="answer-A" bind:value={binder.answerA} />
    <div class="error">{error.answerA}</div>
  </div>

  <div class="input-form">
    <label for="answer-B">Answer B</label>
    <input type="text" id="answer-B" bind:value={binder.answerB} />
    <div class="error">{error.answerB}</div>
  </div>

  <button type="submit">Add Form</button>
</form>

<style>
  form {
    width: 450px;
    margin: 0 auto;
    text-align: center;
  }
  .input-form {
    margin: 15px auto;
  }
  input {
    width: 100%;
    border-radius: 6px;
    padding: 5px;
  }
  label {
    text-align: left;
    display: block;
    margin-bottom: 5px;
  }
  .error {
    color: red;
    font-size: 14px;
  }
</style>
