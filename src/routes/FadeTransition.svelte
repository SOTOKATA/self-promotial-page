<script lang="ts">
    import type { Snippet } from 'svelte';
    import { fly } from 'svelte/transition';
    import { cubicOut } from 'svelte/easing';

    let { key, hash, children }: { key: any, hash: string, children: Snippet } = $props();

    const hasHash = $derived(hash.length != 0);
</script>

{#if hasHash}
    <div>{@render children()}</div>
{:else}
    {#key key}
        <div in:fly={{ y: 20, duration: 300, delay: 200, easing: cubicOut }}
             out:fly={{ y: -20, duration: 200, easing: cubicOut }}>
            {@render children()}
        </div>
    {/key}
{/if}