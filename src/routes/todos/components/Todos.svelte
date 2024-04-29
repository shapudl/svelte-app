<script>
	import { onMount } from 'svelte';

	let todos = [];

	onMount(async () => {
		const response = await fetch('https://dummyjson.com/todos');
		const data = await response.json();
		console.log(data.todos);
		todos = data.todos;
	});
</script>



{#if todos.length > 0}
	<ul>
		{#each todos as todo}
			<li class={todo.completed && 'completed'}>{todo.todo} ({todo.completed})</li>
		{/each}
	</ul>
{:else}
	<p>No todos found.</p>
{/if}

<style>
	ul {
		list-style: none;
		margin: 20px 0;
		padding: 0;
		max-width: min(80%, 800px);
		margin: 0 auto;
	}

	ul li {
		color: white;
		font-weight: 500;
		margin: 2px 0 25px;
		background-color: #90b33d;
		padding: 15px;
		border-bottom: 5px solid #ffab10;
		text-transform: uppercase;
		border-radius: 5px;
		box-shadow: 0px 5px 10px 2px rgba(0, 0, 0, 0.4);
	}

	ul li.completed {
		border-bottom: 5px solid #ad1;
		opacity: 0.8;
	}

	input[type='text'] {
		color: #999;
		padding: 1em;
		margin: 1em 0;
		background-color: #eee;
		font-weight: bold;
		text-transform: uppercase;
	}
</style>
