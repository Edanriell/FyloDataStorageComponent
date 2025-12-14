<script lang="ts">
    import {Button, Logotype} from "@shared/ui";

    interface Props {
        usedStorageAmount: number;
        totalStorageAmount?: number;
        class?: string;
    }

    let {usedStorageAmount, totalStorageAmount = 1000, class: className = ""}: Props = $props();

    const percentage = $derived(
        Math.min(
            100,
            Math.max(0, (usedStorageAmount / totalStorageAmount) * 100)
        )
    );
</script>

<article
        class={`relative flex flex-col gap-y-[1rem] desktop:flex-row desktop:gap-x-[2rem] desktop:items-end ${className}`}>
    <h2 class="sr-only">Used storage</h2>
    <div class="flex flex-col pl-[2.5rem] pb-[2.554rem] pt-[2.554rem] pr-[6.875rem] bg-[var(--colors-blue-850)] shadow-[0_4.688rem_6.25rem_-1.875rem_rgba(0,0,0,0.25)] rounded-[0.625rem_6.25rem_0.625rem_0.625rem] gap-y-[2rem] tablet:max-w-[21.875rem] desktop:pr-[8.375rem]">
        <Logotype/>
        <ul class="flex flex-row gap-x-[1rem]">
            <li class="relative">
                <Button class="w-[3rem] h-[3rem] flex items-center justify-center">
                    <svg class="w-[1.25rem] h-[1.5rem] block! relative" fill="none" height="24" viewBox="0 0 20 24"
                         width="20"
                         xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.9902 0L19.1846 7.19434V21.583C19.1846 22.9079 18.112 23.9813 16.7871 23.9814H2.38574C1.06097 23.9812 0 22.9078 0 21.583L0.0117188 2.39844C0.0117188 1.07344 1.07349 0 2.39844 0H11.9902ZM10.792 8.39355H17.3867L10.792 1.79883V8.39355Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
            <li class="relative">
                <Button class="w-[3rem] h-[3rem] flex items-center justify-center">
                    <svg class="w-[1.25rem] h-[1.5rem] block! relative" fill="none" height="20" viewBox="0 0 24 20"
                         width="24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M21.6 2.40002H12L9.59995 0H2.39996C1.07398 0 0.0119812 1.07398 0.0119812 2.40002L0 16.8C0 18.126 1.07398 19.2 2.40002 19.2H21.6C22.926 19.2 24 18.126 24 16.8V4.80003C24 3.47405 22.926 2.40002 21.6 2.40002Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
            <li class="relative">
                <Button class="w-[3rem] h-[3rem] flex items-center justify-center">
                    <svg class="w-[1.25rem] h-[1rem] block! relative" fill="none" height="16" viewBox="0 0 24 16"
                         width="24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M12 0C15.7 0 18.7004 2.6 19.4004 6C21.9002 6.2002 24 8.40014 24 11C24 13.8 21.8 16 19 16H6C2.7 16 0 13.3 0 10C0 6.9 2.30039 4.4 5.40039 4C6.60042 1.60009 9.10006 0 12 0ZM7 9H10V13H14V9H17L12 4L7 9Z"
                              fill="#697ED4"/>
                    </svg>
                </Button>
            </li>
        </ul>
    </div>
    <div class="relative bg-[var(--colors-blue-850)] shadow-[0_4.688rem_6.25rem_-1.875rem_rgba(0,0,0,0.25)] rounded-[0.625rem] px-[2rem] py-[2.5rem] tablet:px-[2.406rem] desktop:w-full">
        <p class="font-[Raleway] font-normal text-[0.875rem] leading-[115%] text-center text-[var(--colors-blue-200)] mb-[1rem] tablet:text-left">
            You’ve used
            <strong class="font-bold!">{usedStorageAmount}
                GB</strong> of
            your
            storage</p>
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
        <div class="absolute bottom-[-2.5rem] left-[50%] translate-x-[-50%] inline-block rounded-[0.625rem] px-[1.531rem] py-[1rem] bg-[var(--colors-white)] shadow-[0_4.688rem_6.25rem_-1.875rem_rgba(0,0,0,0.25)] desktop:bottom-[unset] desktop:top-[-2.438rem] desktop:left-[unset] desktop:right-[2.5rem] desktop:translate-x-[unset] desktop:rounded-[0.625rem_0.625rem_0_0.625rem]">
            <span class="flex flex-row items-center gap-x-[0.5rem] font-[Raleway] font-bold text-[0.75rem] leading-[115%] tracking-[0.08em] text-[var(--colors-blue-950)] uppercase text-nowrap">
                <strong
                        class="font-bold text-[2.5rem]! leading-[100%]! text-[var(--colors-blue-950)]!">{totalStorageAmount - usedStorageAmount}</strong>
                <span class="opacity-[0.5]">Gb left</span>
            </span>
            <svg class="hidden desktop:block absolute bottom-[-198px] right-[-100.5px]"
                 fill="none"
                 height="223"
                 preserveAspectRatio="none"
                 viewBox="0 0 223 223"
                 width="223" xmlns="http://www.w3.org/2000/svg">
                <g filter="url(#filter0_d_42139_106)">
                    <path clip-rule="evenodd" d="M100 25L122.661 47.6609V25H100Z" fill="white" fill-rule="evenodd"/>
                </g>
                <defs>
                    <filter color-interpolation-filters="sRGB" filterUnits="userSpaceOnUse" height="222.661"
                            id="filter0_d_42139_106" width="222.661"
                            x="0" y="0">
                        <feFlood flood-opacity="0" result="BackgroundImageFix"/>
                        <feColorMatrix in="SourceAlpha" result="hardAlpha" type="matrix"
                                       values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"/>
                        <feOffset dy="75"/>
                        <feGaussianBlur stdDeviation="50"/>
                        <feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.24776 0"/>
                        <feBlend in2="BackgroundImageFix" mode="normal" result="effect1_dropShadow_42139_106"/>
                        <feBlend in="SourceGraphic" in2="effect1_dropShadow_42139_106" mode="normal" result="shape"/>
                    </filter>
                </defs>
            </svg>
        </div>
    </div>
</article>