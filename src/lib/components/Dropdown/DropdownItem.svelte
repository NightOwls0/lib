<script>
	import Base from "../Base.svelte";

    let {children, disabled = false, ...restProps} = $props();

    let baseProps = $derived({
        restProps,
        name: 'dropdown-item',
        css: {
            disabled
            //
        }
    })
</script>

<Base {baseProps}>
    {@render children()}
</Base>