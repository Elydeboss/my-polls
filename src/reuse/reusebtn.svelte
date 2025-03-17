<script>
  import { ChartColumnDecreasing } from "lucide-react";

  let binder = {question: '', answerA: '', answerB: '' };
  let error = {question: '', answerA: '', answerB: '' };
  let validator = false;

  const formSumbit = () => {
    validator = true;
    //validate question
    if (binder.question.trim().length < 6) {
       validator = false;
       error.question = 'inclued atleast 6 ChartColumnDecreasing';
    } else {
      error.question = '';
      
    }

        //validate answerA
        if (binder.answerA.trim().length < 1) {
       validator = false;
       error.answerA = 'can not be empty';
    } else {
      error.answerA = '';
      
    }

        //validate answerB
        if (binder.answerB.trim().length < 1) {
       validator = false;
       error.answerB = 'can not be empty';
    } else {
      error.answerB = '';
      
    }
  }
  
</script>

<form on:submit|preventDefault={formSumbit}>
    <div class="input-form">
        <label for="head-questions">Question</label>
        <input type="text" id="questions" bind:value={binder.question}>
        <div class="error">{ error.question }</div>
    </div>

    <div class="input-form">
        <label for="answer-A">Answer A</label>
        <input type="text" id="answer-A" bind:value={binder.answerA}>
        <div class="error">{ error.answerA} </div>
    </div>

    <div class="input-form">
        <label for="answer-B">Answer B</label>
        <input type="text" id="answer-B" bind:value={binder.answerB}>
        <div class="error">{ error.answerB}</div>
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