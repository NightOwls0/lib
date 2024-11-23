<script>
	import Base from "../Base.svelte";

    let {children, ...restProps} = $props()

    let baseProps = $derived({
        restProps,
        name: 'tab-content'
    })
</script>

<Base {baseProps}>
    {@render children()}
</Base>