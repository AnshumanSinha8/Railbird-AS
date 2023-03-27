<!-- TODO: Still need to figure out why the contractHeight/newHeight is working so funky  it's growing in size and not shrinking ever until it reaches 246px and then just stops??????
<script>
  import { onMount } from 'svelte';
  let contractsHeight = 0;
  
  onMount(() => {
    const contracts = document.getElementById('contracts');
    adjustHeight(contracts);

    window.addEventListener('resize', () => {
      adjustHeight(contracts);
    });
  });

  $: contractsStyle = `height: ${contractsHeight}px`;
  
  function adjustHeight(element) {
    const windowHeight = window.innerHeight;
    const footer = document.getElementById('footer');
    const footerPosition = footer.getBoundingClientRect().top + window.pageYOffset;
    const dynamicDifference = 200 + windowHeight - footerPosition;
    const newHeight = Math.max(windowHeight - footerPosition - 5, dynamicDifference);
    
    if (element) {
      const { top, bottom } = element.getBoundingClientRect();
      contractsHeight = Math.min(newHeight, bottom - top);
    }
  }
</script>

<div class="contracts-on-the-market" id="contracts" style="{contractsStyle}"></div>

<style>
  .contracts-on-the-market {
    display: block;
    width: 100%;
    margin-top: 10px;
    border: 1px solid black;
    border-radius: 12px;
  }
</style> -->

<script>
  import AvailableContract from "./AvailableContract.svelte";

  let contracts = {};

  for (let i = 1; i <= 100; i++) {
    contracts[`Contract #${i}`] = [
    `$${Math.floor(Math.random() * 201)}`,
    Math.floor(Math.random() * 10001)]
  }
</script>

<div class="contracts-on-the-market" id="contracts">
  <h2 class="Market-title">Contracts Available on the Market</h2>
  {#each Object.entries(contracts) as [key, values]}
  <AvailableContract 
    key={key} 
    name={key} 
    values={values}/>
  {/each}
</div>

<style>
  .contracts-on-the-market {
    justify-content: center;
    display: flex;
    flex-wrap: wrap;
    width: 100%;
    height: 200px;
    margin-top: 10px;
    border: 1px solid black;
    border-radius: 12px;
    overflow-y: scroll;
  }

  .Market-title {
    border-bottom: 1px dotted black;
    margin:0;
    padding:0;
    width: 100%;
    text-align: center;
  }
</style>