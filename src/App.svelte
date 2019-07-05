<script>
	import SmartComplete from "./SmartComplete.svelte";
	let input = "";
	let debug = "";
	let events = 0;
	let users = [
		{
			image: "https://thispersondoesnotexist.com/image",
			name: "John Doe",
			uid: "jdoe"
		}, {
			name: "Max Mustermann",
			uid: "mmus"
		}, {
			name: "Markus Lang",
			uid: "mlan"
		}, {
			name: "Joachim Mustermann",
			uid: "jmus"
		}
	];

	const keydown = function (e) {
		debug = ["type", "which", "key", "keyCode", "char", "charCode", "code"].map(x=>`${x}: ${JSON.stringify(e[x])}`).join("\n");
		events++;
	}
</script>

<style>
	textarea {
		width: 100%;
	}
</style>

<textarea bind:value={input} on:keydown={keydown} type="text"></textarea>
<pre>
input: {JSON.stringify(input)}
length: {input.length}
events: {events}

{debug}
</pre>

<SmartComplete bind:users={users}/>
