<script>
	import Button from "./Button.svelte"
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	let genericmessage = '';
		genericmessage: String;
	let apiResults, URL = "http://127.0.0.1:8000";

	const getApiAsync = async (URL) => {
		 const res = await fetch("http://127.0.0.1:8000")
		 const data = await res.json();
		 console.log(data);
		 
		 genericmessage = data
		 return data;
			
			
	};

	const handleClick = () => {
			getApiAsync(URL);
			
			console.log(apiResults)
			

	}

	
	
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<span class="welcome">
			<picture>
				<source srcset={welcome} type="image/webp" />
				<img src={welcome_fallback} alt="Welcome" />
			</picture>
		</span>

		to your new<br />SvelteKit app
	</h1>
	
	<input bind:value={genericmessage} placeholder="Message display window" />
	
	<main>
		<Button on:click={handleClick}> Press to get a message </Button>
	</main>
	
	


	
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}
</style>
