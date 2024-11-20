<script>
	import Base from "./Base.svelte";
    let {title, icon, children, variant = 'default', ...rest} = $props()

    let baseProps = $derived({
        ...rest,
        name: 'alert',
        tag: 'div',
        css: {variant}
    })

</script>
<Base {baseProps}>
    {#if icon}
        <!-- // render icon -->
    {/if}
    <div class="{baseProps.name}-title">{title}</div>
    <div class="{baseProps.name}-description">{@render children()}</div>
</Base>