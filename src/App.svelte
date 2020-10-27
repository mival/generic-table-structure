<script>
  import Grid from "./Grid.svelte";
  import Table from "./Table.svelte";

	export let albums = [], posts = [];


  const loadData = async () => {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/posts?userId=1"
    );
    if (response.ok) {
      posts = await response.json();
    } else {
      const errorText = await response.text();
      throw Error(errorText);
    }
  };

  loadData();

  const loadAlbums = async () => {
    const response = await fetch(
      "https://jsonplaceholder.typicode.com/albums?userId=1"
    );
    if (response.ok) {
      albums = await response.json();
    } else {
      const errorText = await response.text();
      throw Error(errorText);
    }
  };

  loadAlbums();

	export const postColumns = [
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
    {
      header: "Body",
      content: row => (`<span class="ellipsis" title="${row.body}">${row.body}</span>`)
    },
  ];

  export const albumColumns = [
    {
      header: "",
      content: row => (`<a href="/album/${row.id}">Detail</a>`)
    },
    {
      header: "ID",
      key: "id",
    },
    {
      header: "Titulek",
      key: "title",
    }
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
      content: item => (`<a href="/post/${item.id}">Detail</a>`)
    }
  ];
</script>

<style>
</style>

<h2>Tabulka</h2>
<Table rows={posts} columnConfig={postColumns} />
-----------------------
<Table rows={albums} columnConfig={albumColumns} />

<h2>Grid</h2>
<Grid items={posts} itemConfig={itemConfig}/>

