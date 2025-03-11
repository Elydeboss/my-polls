<script>
  //import { createEventDispatcher } from "svelte";
  //const dispatch = createEventDispatcher();
   export let items;
   export let activePolls;
</script>

<div class="div-tab">

    {#each items as item, index}
    <button 
      class="tab-button {index === activePolls ? 'active' : ''}" 
      on:click={() => activePolls = index}
    >
      {item}
    </button>
  {/each}

     <!--     {#each items as item}
            content here 
            <li>
                <div class:active={item === activePolls}>{item}</div>
            </li>
        {/each} -->
</div>

<style>
  /*  .div-tab{
        margin-bottom: 40px;
    }
    .active{
        border-bottom: 3px solid pink;
        padding-bottom: 8px;
    }*/

  .div-tab{
    display: flex;
    justify-content: center; /* Centers horizontally */
    align-items: center; /* Centers vertically */
    gap: 10px;
    border-bottom: 2px solid #ddd;
    padding-bottom: 5px;
    padding-top: 20px;
  }
  .tab-button {
    padding: 8px 16px;
    border: none;
    background: transparent;
    cursor: pointer;
    font-size: 16px;
    color: pink;
  }
  .tab-button.active {
    color: black;
    font-weight: bold;
    border-bottom: 2px solid red;
  }
</style>