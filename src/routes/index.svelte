<script>
    import '../app.css' 
    import { isOverlayOpen } from '../stores/overlay-store'
</script>

<button class="bg-purple-800 text-white py-2 px-6 rounded-md" on:click={() => isOverlayOpen.set(true)}>Open</button>