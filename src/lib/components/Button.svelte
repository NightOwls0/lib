<script lang="ts">
	import type { Snippet } from 'svelte';
	import Base from './Base.svelte';

	interface $$Props {
		href: string;
		variant: 'primary' | 'ghost' | 'secondary' | 'link' | 'destructive';
		size: 'default' | 'sm' | 'icon';
		icon: boolean;
		children: Snippet;
	}

	let {
		href,
		size = 'default',
		icon,
		variant = 'primary',
		children,
		...rest
	}: $$Props | any = $props();

	let baseProps = $derived({
		...rest,
		href,
		tag: href ? 'a' : 'button',
		name: 'button',
		css: {
			variant, size, icon
		}
	})

</script>

<Base {baseProps}>
	{@render children()}
</Base>