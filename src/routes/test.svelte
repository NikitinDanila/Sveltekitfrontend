<script>
	let apiResults, URL = "https://api.themoviedb.org/3/trending/tv/week";

	const getApiAsync = (URL) => {
		 fetch(URL)
			.then((response) => response.json())
			.then((response) => apiResults = response);
	};

	const handleClick = () => {
			getApiAsync(URL);
	}

	$: apiResults;
</script>

<main>
	<button on:click={handleClick}>GetAPI</button>

	<!-- // This is just for showing results -->
	<div>{apiResults ? JSON.stringify(apiResults, null, 2) : ""}</div>
</main>