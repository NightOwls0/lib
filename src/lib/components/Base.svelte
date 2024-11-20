<script lang="ts">
    import {cls} from '$lib/helpers.js'

    let {baseProps, children} = $props();
    let {tag = 'div', name, css, class: klass, ...rest} = baseProps

</script>

<svelte:element this={tag} class={cls(name, css, klass)} {...rest}>
    {@render children()}
</svelte:element>