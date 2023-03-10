<script>
  import { createEventDispatcher } from 'svelte';
  export let name;
  export let values;
  export let onClick;

  const dispatch = createEventDispatcher();

  function handlePurchase() {
    dispatch('purchase', { name, values });
    onClick();
  }

  function handleWatchlist() {
    dispatch('watchlist', { name, values });
    onClick();
  }
</script>

<div class="available-contract">
  <h4>{name}:</h4>
  <ul>
    {#each values as value, index}
      <li>
        {#if index === 0}
          Price: {value}
        {:else}
          Daily Volume:{value}
        {/if}
      </li>
    {/each}
  </ul>
  <div class="buttons">
    <button class="purchase-button" on:click={handlePurchase}>Purchase</button>
    <button class="watchlist-button" on:click={handleWatchlist}>Watch</button>
  </div>
</div>

<style>
    .available-contract {
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 15%;
        background: #655DBB;
        border-radius: 18px;
        margin: 8px;
        padding: 5px;
    }
    
    h4 {
      margin: 0;
      padding-right: 5px;
    }
    
    ul {
      list-style: none;
      margin: 0;
      padding: 0;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    
    li {
      margin: 5px;
      padding: 5px;
    }
    
    .buttons {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      width: 100%;
      margin-left: auto;
    }
    
    .purchase-button,
    .watchlist-button {
      background-color: #BFACE2;
      border: 1px solid black;
      border-radius: 5px;
      padding: 5px 10px;
      font-size: 14px;
      cursor: pointer;
    }
    
    .purchase-button:hover,
    .watchlist-button:hover {
      background-color: #d2f2d6;
    }
</style>