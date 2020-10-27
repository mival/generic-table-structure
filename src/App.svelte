<script>
  import Grid from "./Grid.svelte";
  import Table from "./Table.svelte";
  const loadData = async () => {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/posts?userId=1"
    );
    if (response.ok) {
      data = await response.json();
    } else {
      const errorText = await response.text();
      throw Error(errorText);
    }
  };

  loadData();

	export let data = [];

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

	export const itemConfig = [
    {
      header: "ID",
      key: "id",
    },
    {
      header: "Titulek",
      key: "title",
		},
		{
      header: "",
      content: item => (`<a class="btn btn-primary" href="/post/${item.id}">Detail</a>`)
    }
  ];
</script>

<style>
</style>

<h2>Tabulka</h2>
<div class="table-wrapper">
	<div class="table-responsive">
		<Table rows={data} columns={columns} htmlOptions = { {class: "table table-bordered table-hover"} }/>
	</div>
</div>
<h2>Grid</h2>
<Grid items={data} itemConfig={itemConfig}/>
