<script>
	export let name;
    import AssetsAndWatchlist from "./Components/AssetsAndWatchlist.svelte";
    import ContractsOnTheMarket from "./Components/ContractsOnTheMarket.svelte";
	import Header from "./Components/Header.svelte"
    import PortfolioOverview from "./Components/PortfolioOverview.svelte";
	import Footer from "./Components/Footer.svelte";
</script>

<main style="display: flex; flex-direction: column;">
	<Header/>
	<div style="display: flex; margin-top: 60px">
		<PortfolioOverview/>
		<AssetsAndWatchlist/>
	</div>
	<ContractsOnTheMarket/>
	<Footer></Footer>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>