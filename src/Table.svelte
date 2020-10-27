<script>
  import TBody from "./TBody.svelte";

  import TFoot from "./TFoot.svelte";

  import THead from "./THead.svelte";

  export let columns,
    rows = [];
  export let htmlOptions = {};
</script>

<table {...htmlOptions}>
  <THead {columns} htmlOptions={{ class: 't-head thead-dark' }} />
  <TBody
    {rows}
    {columns}
    htmlOptions={{ class: 't-body' }}
    rowOptions={{ class: 'tr' }} />
  <TFoot />
</table>
