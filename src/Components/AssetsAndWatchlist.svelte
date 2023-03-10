<script>
  import Assets from "./Assets.svelte";
  import Watchlist from "./Watchlist.svelte";

  let currentTime = new Date();
    function updateTime() {
        currentTime = new Date();
  }

  let assetsView = true;
  let assetsContent = "Content for the assets view";
  let watchlistContent = "Content for the watchlist view";

  function toggleView() {
    assetsView = !assetsView;
  }
  setInterval(updateTime, 1000);
</script>
<div class="assets-and-watchlist">
  <div class="toggle-container">
    <button on:click={toggleView}>Switch View</button>
  </div>
  {#if assetsView}
    <div class="assets-title-container">
      <h2 class="Assets-title">Your Assets</h2>
      <h3 class="market-timer-information"> {currentTime.toLocaleTimeString()}</h3>
    </div>
    <Assets content={assetsContent} />
  {:else}
    <div class="watchlist-title-container">
      <h2 class="Watchlist-title">Your Watchlist</h2>
      <h3 class="market-timer-information"> {currentTime.toLocaleTimeString()}</h3>
    </div>
    <Watchlist content={watchlistContent} />
  {/if}
</div>

<style>
  .assets-and-watchlist {
    height: 400px;
    width: 40.5%;
    float: right;
    border: 1px solid black;
    border-radius: 12px;
    position: relative;
    overflow: hidden;
  }

  .assets-and-watchlist::after {
    content: "";
    display: block;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 0;
  }

  .toggle-container {
    position: absolute;
    top: 0;
    left: 0;
    border-right: 1px solid black;
    border-top-left-radius: 12px;
    border-bottom-right-radius: 18px;
    background-color: #4d67b3;
    padding: 5px;
  }

  button {
    border: none;
    background-color: #4d67b3;
    font-size: 12px;
    cursor: pointer;
  }

  .watchlist-title-container,
  .assets-title-container {
    display: flex;
    justify-content: left;
    align-items: center;
    height: 41px;
    border-bottom: 1px dotted black;
    text-align: center;
  }


  .Watchlist-title,
  .Assets-title {
    margin:0;
    padding:0;
    width: 100%;
    text-align: center;
  }
</style>