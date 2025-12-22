<script lang="ts">
    import {resolve} from "$app/paths";
    import {goto} from "$app/navigation";

    const status = 404;
    const message = "Page not found";
</script>

<div class="relative z-10 w-full min-h-screen flex flex-col items-center justify-center text-center px-6">
    <h1 class="text-[96px] sm:text-[120px] font-extrabold text-cyan-300 leading-none">
        {status}
    </h1>
    <p class="mt-6 text-2xl sm:text-3xl font-semibold text-white/90">
        {message}
    </p>
    <p class="mt-3 text-base text-lg text-white/60 max-w-md text-pretty">
        The page you are looking for does not exist or has been moved.
    </p>
    <button
            class="mt-10 px-8 py-4 rounded-xl
		       bg-white/10 text-white font-medium
		       backdrop-blur border border-white/20
		       hover:bg-white/20 hover:border-white/40
		       transition active:scale-95"
            onclick={() => goto(resolve("/"))}
    >
        Return Home
    </button>
</div>
