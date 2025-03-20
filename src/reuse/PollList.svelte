<script>
  export let Polls = [];
   
</script>

<div class="poll-list">
    {#each Polls as poll(Polls.id)}
         <!-- content here -->
       <div>{ Polls.question }</div>
    {/each}
</div>

<style>

</style>