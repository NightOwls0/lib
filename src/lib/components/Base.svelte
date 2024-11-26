<script lang="ts">
    import {cls} from '$lib/helpers.js'

    let {
        element = $bindable(),
        baseProps, 
        children
    } = $props();
    let {tag = 'div', name, css = {}, restProps = {}, ...rest} = $derived(baseProps)
    let {class: klass, ...rest2} = $derived(restProps)

</script>

<svelte:element bind:this={element} this={tag} class={cls(name, css, klass)} {...rest} {...rest2}>
    {@render children()}
</svelte:element>