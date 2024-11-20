<script>
	import Base from "./Base.svelte";

    let {variant = 'primary', children, ...rest} = $props()

    let baseProps = $derived({
        ...rest,
        tag: 'span',
        name: 'badge',
        css: {
            variant,
        }
    })
</script>
<Base {baseProps}>
    {@render children()}
</Base>