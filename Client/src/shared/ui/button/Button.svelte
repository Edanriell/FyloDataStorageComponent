<script lang="ts">
    import type {Snippet} from "svelte";

    interface Props {
        class?: string;
        children: Snippet;
    }

    let {children, class: className = ""}: Props = $props();
</script>

<button
        class={`rounded-[10px] bg-[var(--colors-blue-950)] ${className}`}
        type="button"
>
    {@render children?.()}
</button>