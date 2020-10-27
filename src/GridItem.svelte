<script>
  export let itemData = {};
  export let itemConfig = [];
</script>

<style>
</style>

<div class="grid__item">
  {#each itemConfig as config}
    {#if config.header}
      <dl>
        <dt>{config.header}</dt>
        <dd>{itemData[config.key]}</dd>
      </dl>
    {:else}
      {@html config.content(itemData)}
    {/if}
  {/each}
</div>
