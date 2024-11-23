<script>
	import Base from './Base.svelte';

	let { variant = 'primary', children, ...restProps } = $props();

	let baseProps = $derived({
		restProps,
		tag: 'span',
		name: 'badge',
		css: {
			variant
		}
	});
</script>

<Base {baseProps}>
	{@render children()}
</Base>
