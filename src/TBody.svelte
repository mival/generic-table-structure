<script>
  export let htmlOptions, rowOptions = {};
  export let columns = [];
  export let rows = [];
</script>

<style>
</style>

<tbody {...htmlOptions}>
  {#each rows as row}
    <tr {...rowOptions}>
      {#each columns as column}
        {#if column.content}
          <td {...column.htmlOptions}>{@html column.content(row)}</td>
        {:else}
          <td {...column.htmlOptions}>{row[column.key]}</td>
        {/if}
      {/each}
    </tr>
  {/each}
</tbody>
