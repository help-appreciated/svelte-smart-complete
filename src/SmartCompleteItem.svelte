<script>
	export let name = "Unknown User";
	export let uid = "";
	export let image = false;
</script>

<style lang="scss">
	a {
		display: flex;
		outline: 1px dotted red;
		color: #000;
		text-decoration: none;

		&:focus, &.focus {
			color: #f50;
		}
		&:hover {
			color: #f00;
		}
	}

	.uid {
		font-size: 60%;
	}
</style>

<a href="/bla/profile/{uid}">
	{#if image}
		<div class="image" style="background-image: url({image})"></div>
	{:else}
		<div class="no-image"></div>
	{/if}
	<div class="name">
		{name}
	</div>
	<div class="uid">
		({uid})
	</div>
</a>
