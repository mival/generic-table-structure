<script>
  export let htmlOptions = {},
    rowOptions = {};
  export let columns = [];
</script>

<style>
</style>

<thead {...htmlOptions}>
  <tr {...rowOptions}>
    {#each columns as column}
      <th>
        {#if column.header}
        <span
          on:click={() => (column.sort = column.sort === 'asc' ? 'desc' : 'asc')}>
          {column.header}
          {#if column.sort === 'asc'}&uarr;{:else}&darr;{/if}
        </span>
        {:else}
          {column.header}
        {/if}
      </th>
    {/each}
  </tr>
</thead>
