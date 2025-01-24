<script>
    import { IconPower } from '@tabler/icons-svelte';
</script>
<section class="min-h-screen flex items-center justify-center lg:justify-between gap-2 lg:gap-14 w-7xl mx-auto px-4 sm:px-6 lg:px-8 z-[1] flex-col-reverse lg:flex-row">
    <div class="flex flex-col gap-6">
        <div>
            <h1 class="text-5xl md:text-7xl text-white font-extrabold">Learn to <span class="text-primary-400">code</span></h1>
            <div class="flex justify-center items-center">
                <h1 class="text-5xl md:text-7xl text-white font-extrabold">the fun way.</h1>
                <button 
                    class="size-10 mt-5 flex justify-center items-center bg-red cursor-pointer select-none active:translate-y-4 active:[box-shadow:0_0px_0_0_#994743,0_0px_0_0_#994743] transition-all duration-150 [box-shadow:0_5px_0_0_#994743,0_10px_0_0_#994743] rounded-full text-xl font-extrabold text-white relative bottom-[10px] ml-2" 
                >
                    <IconPower />
                </button>
            </div>
        </div>
        <p class="text-primary-100 text-lg md:text-xl max-w-[300px] md:max-w-[350px]">
            Bring any idea to life through the power of programming.
        </p>
        <a 
            class="w-52 h-14 mt-5 flex justify-center items-center bg-primary-400 cursor-pointer select-none active:translate-y-4 active:[box-shadow:0_0px_0_0_#38809A,0_0px_0_0_#38809A] transition-all duration-150 [box-shadow:0_5px_0_0_#38809A,0_10px_0_0_#38809A] rounded-xl text-xl font-extrabold text-white" 
            href="#contact"
        >
            Get started
        </a>
    </div>
    <div class="">
        <img src="/hero.svg" alt="">

    </div>
</section>
