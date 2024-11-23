<script>
	import Base from '../Base.svelte';

	let { children, ...restProps } = $props();

	let baseProps = $derived({
		restProps,
		name: 'tab-header',
		tag: 'aside',
	})
	let navProps = $derived({
		name: 'tab-list',
		tag: 'nav'
	})
</script>

<Base {baseProps}>
	<Base baseProps={navProps}>
        {@render children()}
	</Base>
</Base>
