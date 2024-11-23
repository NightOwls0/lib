<script lang="ts">
	import type { Snippet } from 'svelte';
	import Base from './Base.svelte';

	interface $$Props {
		href: string;
		variant: 'primary' | 'ghost' | 'secondary' | 'link' | 'destructive';
		size: 'default' | 'sm' | 'icon';
		icon: boolean;
		type: 'button' | 'submit'
		children: Snippet;
	}

	let {
		href,
		size = 'default',
		icon,
		variant = 'primary',
		type = 'button',
		children,
		...restProps
	}: $$Props | any = $props();

	let baseProps = $derived({
		restProps,
		href,
		tag: href ? 'a' : 'button',
		type,
		name: 'button',
		css: {
			variant, size, icon
		}
	})

</script>

<Base {baseProps}>
	{@render children()}
</Base>