<script>
	import SmartCompleteItem from "./SmartCompleteItem.svelte";
	export let users;
	export let width = "300px";
</script>

<style>
	div {
		position: absolute;
	}
</style>

<div style="width: {width}">
	{#each users as user}
		<SmartCompleteItem {...user}/>
	{/each}
</div>
