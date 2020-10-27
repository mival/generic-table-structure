<script>
  export let htmlOptions, rowOptions = {};
  export let columns = [];
</script>

<style>
</style>

<tfoot {...htmlOptions}>
  <tr {...rowOptions}>
    {#each columns as column}
      <th>{column.header}</th>
    {/each}
  </tr>
</tfoot>
