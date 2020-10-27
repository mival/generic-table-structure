<script>
  import TBody from "./TBody.svelte";

  import TFoot from "./TFoot.svelte";

  import THead from "./THead.svelte";



  export let rows = [];
  export const columns = [
    {
      header: "",
      content: row => (`<a href="/post/${row.id}">Detail</a>`)
    },
    {
      header: "ID",
      key: "id",
    },
    {
      header: "Titulek",
      key: "title",
    },
  ];
</script>

<table>
  <THead {columns} htmlOptions={ {class: 't-body'} } />
  <TBody {rows} {columns} htmlOptions={ {class: 't-body'} } rowOptions={ {class: 'tr'} } />
  <TFoot />
</table>
