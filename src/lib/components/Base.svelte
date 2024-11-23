<script lang="ts">
    import {cls} from '$lib/helpers.js'

    let {baseProps, children} = $props();
    let {tag = 'div', name, css = {}, class: klass, restProps, ...rest} = $derived(baseProps)

</script>

<svelte:element this={tag} class={cls(name, css, klass)} {...restProps} {...rest}>
    {@render children()}
</svelte:element>