<script module>
    export const MODAL = {};
</script>
<script>
	import { writable } from "svelte/store";
	import Base from "../Base.svelte";
	import { setContext } from "svelte";

    let {children, open = $bindable(false), ...restProps} = $props();

    let isOpen = writable(open)

    $effect(() => {$isOpen = open})
    $effect(() => {open = $isOpen})

    setContext(MODAL, {isOpen})

    let baseProps = $derived({
        restProps,
        name: 'modal',
        css: { open }
    })
</script>

<Base {baseProps}>
    {@render children()}
</Base>