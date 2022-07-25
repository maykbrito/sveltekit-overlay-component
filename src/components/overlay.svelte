<script>
    import { fly } from 'svelte/transition';
    import { isOverlayOpen } from '../stores/overlay-store'

    const handleKeydown = event => {
        const key = event.key;
		const keyCode = event.keyCode;

        if(key === 'Escape') {
            isOverlayOpen.set(false)
        }
    }

</script>

<svelte:window on:keydown={handleKeydown}/>

<div class="w-screen h-screen fixed inset-0 flex justify-center items-center bg-gray-100 opacity-90 z-10" on:click={() => isOverlayOpen.set(false)}>
    <div 
        transition:fly="{{ y: 200, duration: 200 }}"
        on:click|stopPropagation
        class="bg-gray-800 text-white max-w-lg rounded-md px-8 py-10 relative opacity-95 ">
        <button
            on:click={() => isOverlayOpen.set(false)} 
            class="absolute top-1 right-3 text-4xl text-gray-300">&times;</button>
        <slot/>
    </div>
</div> 