<script>
  export let htmlOptions = {}, rowOptions = {};
  export let columnConfig = [];
</script>

<style>
</style>

<tfoot {...htmlOptions}>
  <tr {...rowOptions}>
    {#each columnConfig as column}
      <th>{column.header}</th>
    {/each}
  </tr>
</tfoot>
