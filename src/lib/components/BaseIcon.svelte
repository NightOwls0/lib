<script>
	import Base from "./Base.svelte";

    let {icons = {}, name, ...restProps} = $props();

    let baseProps = $derived({
        restProps,
        name: 'base-icon',
        css: {
            //
        }
    })
</script>

<Base {baseProps}>
    {#if icons[name]}
        {@html icons[name].replace('width="32"', '').replace('height="32"', '')}
    {/if}
</Base>