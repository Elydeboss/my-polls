<script>
  let binder = {question: '', answerA: '', answerB: '' };

  const formSumbit = () => {
    console.log(binder)
  }
</script>

<form on:submit|preventDefault={formSumbit}>
    <div class="input-form">
        <label for="head-questions">Question</label>
        <input type="text" id="questions" bind:value={binder.question}>
    </div>

    <div class="input-form">
        <label for="answer-A">Answer A</label>
        <input type="text" id="answer-A" bind:value={binder.answerA}>
    </div>

    <div class="input-form">
        <label for="answer-B">Answer B</label>
        <input type="text" id="answer-B" bind:value={binder.answerB}>
    </div>

    <button>Add form</button>

</form>

<style>
  form{
    width: 450px;
    margin: 0 auto;
    text-align: center;
  }
  .input-form{
    margin: 15px auto;
  }
  input{
    width: 100%;
    border-radius: 6px;
  }
  label{
    text-align: left;
  }
</style>