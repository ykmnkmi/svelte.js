<script>
	function throw_error() {
		throw new Error('test')
	}

	let count = $state(0);
	let onerror = $state((e) => console.log('error caught'));
</script>

<svelte:boundary {onerror}>
	{count > 0 ? throw_error() : null}
</svelte:boundary>

<button onclick={() => count++}>+</button>
<button onclick={() => onerror = () => console.log('error caught!!!')}>change error message</button>


