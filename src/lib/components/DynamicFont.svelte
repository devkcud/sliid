<script lang="ts">
    import { onMount } from 'svelte';

    export let text = '';
    let fontSize: number;

    text = text.split(':sliid:').join('🚀');
    text = text.split(':cool:').join('😎');
    text = text.split(':nerd:').join('🤓');

    function updateFontSize() {
        const windowWidth = window.innerWidth;
        const textLength = text.length;
        fontSize = (windowWidth / textLength) * 2; // Adjust this multiplier as needed

        fontSize = Math.max(24, Math.min(156, fontSize));
    }

    onMount(() => {
        updateFontSize();
        window.addEventListener('resize', updateFontSize);
    });
</script>

<div class="container">
    <div class="text" style="font-size: {fontSize}px">{text}</div>
</div>

<style>
    .container {
        padding: 5rem;
    }

    .text {
        text-align: center;
        word-wrap: break-word;
    }
</style>
