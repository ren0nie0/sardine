<script>
	import { getContext } from 'svelte';
	import { TABS } from './Tabs.svelte';

	const tab = {};
	const { registerTab, selectTab, selectedTab } = getContext(TABS);

	registerTab(tab);
</script>

<style>
	button {
		background: none;
		border: none;
		border-radius: 0;
		margin: 0;
		width: 8vh;
		color: white;
	}
	
	.selected {
		border-bottom: 2px solid white;
		color: white;
	}
</style>

<button class:selected="{$selectedTab === tab}" on:click="{() => selectTab(tab)}">
	<slot></slot>
</button>