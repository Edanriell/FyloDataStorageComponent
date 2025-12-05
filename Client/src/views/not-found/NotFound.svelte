<script lang="ts">
    import {goto} from "$app/navigation";

    const status = 404;
    const message = "Page not found";
</script>

<div class="w-full min-h-screen flex flex-col items-center justify-center text-center px-4 bg-[#f6f5f6]">
    <h1 class="text-[100px] font-extrabold text-gray-700">
        {status}
    </h1>
    <p class="mt-4 text-2xl text-gray-600">
        {message}
    </p>
    <p class="mt-2 text-gray-500">
        The page you are looking for does not exist.
    </p>
    <button
            class="mt-10 px-6 py-3 border border-gray-400 text-gray-700 rounded-lg
		       hover:bg-gray-200 transition active:scale-95"
            on:click={() => goto('/')}
    >
        Return Home
    </button>
</div>