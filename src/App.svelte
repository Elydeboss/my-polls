<script>
	import Head from "./head.svelte";
	import Foot from "./footer.svelte";
	import Tabs from "./reuse/tabs.svelte";
	import Use from "./reuse/reusebtn.svelte"
  import { handler } from "tailwindcss-animate";

	let activePolls = 0;
    let tabContent = ["Current Polls Content", "Add New Poll Content"];

   let voteHandle = (e) => {
     const pollVote = e.detail;
	 polls = [pollVote, ...polls]
	 console.log(polls)
   }

   let Polls = [{id: 1, question: 'what programming language do you like', answerA: 'python', answerB:'javascript', votesA:10, voteB: 18, }];
</script>

<Head />
<main>
	<Tabs bind:activePolls items={["Current Polls", "Add New Poll"]} />

	<div class="tab-content">
	  {#if activePolls === 0}
		<p>{tabContent[0]}</p>
	  {:else}
		<Use on:pollVote={voteHandle}/>
	  {/if}
	</div>

</main>

<Foot />

<style>
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
	
	.tab-content{}
</style>