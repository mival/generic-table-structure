<script>
import GridItem from "./GridItem.svelte";

  export let items, itemConfig = [];
</script>
<style>

</style>

<div class="grid">
  {#each items as item}
    <GridItem itemData={item} itemConfig={itemConfig}/>
  {/each}
</div>