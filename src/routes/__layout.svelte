<script>
    import Overlay from "../components/overlay.svelte";
    import { isOverlayOpen } from "../stores/overlay-store";
</script>

{#if $isOverlayOpen}
    <Overlay>
        <p>I'm overlay content </p>
    </Overlay>
{/if}
<main class="container mx-auto mt-6">
    <slot></slot>
</main>