<script lang="ts">
    import type {Snippet} from 'svelte';

    interface Props {
        class?: string;
        children: Snippet;
    }

    let {children, class: className = ''}: Props = $props();
</script>

<button
        class={`block rounded-[10px]
	        bg-[var(--colors-blue-950)] text-white
	        cursor-pointer
	        transition-all duration-200 ease-out
	        hover:bg-[var(--colors-blue-900)]
	        hover:shadow-lg hover:shadow-black/30
	        active:scale-[0.97]
	        focus:outline-none focus:ring-2 focus:ring-cyan-400/40
	        ${className}`}
        type="button"
>
    {@render children?.()}
</button>
