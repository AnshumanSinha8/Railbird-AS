<script>
    export let name;
    export let values;
    export let type;
  </script>
  
  <div class="claimed-asset">
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
  </div>
  
  <style>
    .claimed-asset {
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
  </style>
  