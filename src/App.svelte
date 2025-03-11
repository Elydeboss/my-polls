<script>
	import Head from "./head.svelte";
	import Foot from "./footer.svelte";
	import Tabs from "./reuse/tabs.svelte";

	let activePolls = 0;
    let tabContent = ["Current Polls Content", "Add New Poll Content"];

</script>

<Head />
<main>
	<Tabs bind:activePolls items={["Current Polls", "Add New Poll"]} />

	<div class="tab-content">
	  {#if activePolls === 0}
		<p>{tabContent[0]}</p>
	  {:else}
		<p>{tabContent[1]}</p>
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