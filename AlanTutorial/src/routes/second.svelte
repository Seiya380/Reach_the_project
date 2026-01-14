<script>
	let { answer } = $props();
</script>

<p>The answer is {answer}</p>

{#if answer === 42}
	<p>The answer of the universe</p>
{/if}
