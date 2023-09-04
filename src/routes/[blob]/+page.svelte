<script>
    import { page } from '$app/stores';
    import DynamicFont from '$lib/components/DynamicFont.svelte';
</script>

<DynamicFont text={$page.params.blob} />
