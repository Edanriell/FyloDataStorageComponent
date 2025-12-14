<script lang="ts">
    import {goto} from "$app/navigation";

    const {error, status} = $props<{
        error: App.Error | null;
        status: number;
    }>();
</script>

<div class="w-full min-h-screen flex flex-col items-center justify-center text-center px-4">
    <h1 class="text-[100px] font-extrabold text-gray-700">{status}</h1>
    <p class="mt-4 text-2xl text-gray-600">
        {error?.message ?? "Something went wrong"}
    </p>
    <p class="mt-2 text-gray-500">
        The page encountered an unexpected issue.
    </p>
    <button
            class="mt-10 px-6 py-3 border border-gray-400 text-gray-700 rounded-lg
		       hover:bg-gray-200 transition active:scale-95"
            onclick={() => goto('/')}
    >
        Return Home
    </button>
</div>