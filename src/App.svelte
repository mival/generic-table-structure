<script lang="ts">
	import Table from "./Table.svelte";
	const loadData = async () => {
		const response = await fetch('https://jsonplaceholder.typicode.com/posts?userId=1');
		if (response.ok) {
			data = await response.json();
		} else {
			const errorText = await response.text();
			throw Error(errorText);
		}
	}

	loadData();

	export let data = [];
</script>

<style></style>

<Table rows={data} />

