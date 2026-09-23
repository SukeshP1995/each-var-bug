<script>
	let human = $state({name: ''})
	const { name } = $derived(human);
</script>
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<h1>Hello {name}!</h1>

<h2>Children</h2>

<button onclick={() => {
	human = {
		"id": 1,
		"name": "Sun",
		"children": [
			{
				"id": 2,
				"name": "Mercury"
			},
			{
				"id": 3,
				"name": "Venus"
			},
			{
				"id": 4,
				"name": "Earth"
			}
		]
	}
}}>
	change human
</button>

	{#each (human.children ?? []) as child (child.name)}
		{const {name} = child;}
		<li>{name}</li>
	{/each}
