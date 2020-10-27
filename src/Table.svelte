<script>
  import TBody from "./TBody.svelte";

  import TFoot from "./TFoot.svelte";

  import THead from "./THead.svelte";



  export let columnConfig,rows = [];
</script>

<table>
  <THead {columnConfig} htmlOptions={ {class: 't-body'} } />
  <TBody {rows} {columnConfig} htmlOptions={ {class: 't-body'} } rowOptions={ {class: 'tr'} } />
  <TFoot />
</table>
