<nav>
	<a href="/">Home</a>
	<a href="/todos">Todos</a>
</nav>

<slot />

<style>
	:global(body) {
        font-family: "Roboto", sans-serif;
        text-align:center;
		background-color: #092021;
		color: #fff;
		padding: 2em;
	}
    :global(a) {
        text-decoration: none;
        color: #ebecb0;
    }
</style>
