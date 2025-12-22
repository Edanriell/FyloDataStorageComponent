<script lang="ts">
    interface Props {
        usedStorageAmount: number;
        totalStorageAmount?: number;
    }

    let {usedStorageAmount, totalStorageAmount = 1000}: Props = $props();

    const percentage = $derived(
        Math.min(
            100,
            Math.max(0, (usedStorageAmount / totalStorageAmount) * 100)
        )
    );
</script>

<div aria-label="Space left in storage"
     aria-valuemax={totalStorageAmount}
     aria-valuemin="0"
     aria-valuenow={totalStorageAmount - usedStorageAmount}
     class="relative"
     role="progressbar">
    <div class="flex flex-col gap-y-[0.5rem]">
        <div class="relative p-[0.188rem] rounded-[0.625rem] w-full h-[1.25rem] bg-[var(--colors-blue-900)]">
            <div class="relative h-[0.875rem] rounded-[0.5rem] bg-[linear-gradient(90deg,_#ffa197_0%,_#ff4a95_100%)] p-[0.125rem]"
                 style={`width: ${percentage}%`}>
                <div class="rounded-full bg-[var(--colors-white)] w-[0.625rem] h-[0.625rem] ml-[auto] mr-[0]"></div>
            </div>
        </div>
        <div class="flex flex-row justify-between">
            <span class="font-[Raleway] font-extrabold text-[0.75rem] leading-[115%] text-[var(--colors-blue-200)] uppercase">0 GB</span>
            <span class="font-[Raleway] font-extrabold text-[0.75rem] leading-[115%] text-[var(--colors-blue-200)] uppercase">{totalStorageAmount}
                GB</span>
        </div>
    </div>
</div>