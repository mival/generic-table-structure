<script>
  export let itemData = {};
  export let itemConfig = [];
</script>

<style>
</style>

<div class="grid__item card">
  <div class="card-body">
    {#each itemConfig as config}
      {#if config.header}
        <h5 class="card-title">{config.header}</h5>
        <p class="card-text">{itemData[config.key]}</p>
      {:else}
        {@html config.content(itemData)}
      {/if}
    {/each}
  </div>
</div>
