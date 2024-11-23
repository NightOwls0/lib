<script>
	import { getContext } from 'svelte';
	import { TABS } from './Tabs.svelte';
	import Base from '../Base.svelte';

	let { children, name, error = false, ...restProps } = $props();

	const { activeTab } = getContext(TABS);

	let baseProps = $derived({
		restProps,
		name: 'tab-panel',
		css: {
			active: $activeTab === name
		}
	})
</script>

<Base {baseProps}>
	{@render children()}
</Base>