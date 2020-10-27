<script>
  import TBody from "./TBody.svelte";

  import TFoot from "./TFoot.svelte";

  import THead from "./THead.svelte";



  export let columns,rows = [];
</script>

<table>
  <THead {columns} htmlOptions={ {class: 't-body'} } />
  <TBody {rows} {columns} htmlOptions={ {class: 't-body'} } rowOptions={ {class: 'tr'} } />
  <TFoot />
</table>
