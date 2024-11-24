<script>
	import { getContext } from "svelte";
	import Base from "../Base.svelte";
	import { MODAL } from "./Modal.svelte";

    let {children, ...restProps} = $props();

    let baseProps = $derived({
        restProps,
        name: 'modal-content',
    })

    let closeButtonProps = $derived({
        name: 'modal-close-button',
        onclick: () => $isOpen = false,
        restProps: {},
    })

    const {isOpen} = getContext(MODAL)

    // TODO: Handle outside click to close modal
</script>

<Base {baseProps}>
    {@render children()}
    <Base baseProps={closeButtonProps}>
        X
    </Base>
</Base>