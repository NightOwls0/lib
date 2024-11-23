<script>
	import { getContext } from 'svelte';
	import { TABS } from './Tabs.svelte';
	import Base from '../Base.svelte';

	let { name, error = false, disabled = false, ...restProps } = $props();

	function activateTab() {
		console.log("activate tab")
		$activeTab = name;
	}

	const { activeTab } = getContext(TABS);

	let baseProps = $derived({
		restProps,
		name: 'tab-item',
		tag: 'button',
		type: 'button',
		onclick: activateTab,
		css: {
			active: $activeTab == name,
			error,
			disabled
		}
	})


</script>


<Base {baseProps}>
	{name} 
</Base>
