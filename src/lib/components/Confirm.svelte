<script lang="ts">
	import Base from './Base.svelte';

	let {
		onclose = () => {},
		open = $bindable(false),
		children,
		...restProps
	} = $props();

	let baseProps = $derived({
		restProps,
		name: 'confirm',
        css: {
            open
        }
	});

	let confirmContentProps = $derived({
        name: 'confirm-content'
    });
	let closeButtonProps = $derived({
        onclick: () => open = !open,
        name: 'confirm-close-button'
    });
</script>

<Base {baseProps}>
	<Base baseProps={confirmContentProps}>
		{@render children()}
        <Base baseProps={closeButtonProps}>
            X
        </Base>
	</Base>
</Base>
