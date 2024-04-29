<nav>
	<a href="/">home</a>
	<a href="/todos">Todos</a>
</nav>

<slot />

<style>
	:global(body) {
		background-color: #092021;
		color: #fff;
		padding: 2em;
	}
	h1 {
		color: #999;
		text-align: center;
	}
</style>
