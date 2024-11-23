<script module>
	export const TABS = {};
</script>

<script>
	import { setContext } from 'svelte';
	import { writable } from 'svelte/store';
	import Base from '../Base.svelte';

	let { active = $bindable(), children, ...restProps } = $props();

	let activeTab = writable(active);

	$effect(() => {
		active = $activeTab;
	});

	$effect(() => {
		$activeTab = active;
	});

	setContext(TABS, { activeTab });

	let baseProps = $derived({
		restProps,
		name: 'tabs'
	});
</script>

<Base {baseProps}>
	{@render children()}
</Base>
