<script lang="ts">
let mobileMenuOpen = $state(false);
import { IconMenu2 } from '@tabler/icons-svelte';
</script>

<nav class="fixed z-50 w-screen backdrop-blur-md z-[2]">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-20 items-center">
            <a class="flex items-center gap-2" href="/">
                <img src="/fav.png" alt="" class="h-12 w-12">
                <span class="text-white text-xl font-black max-w-40 leading-5">
                    BUILD THE <span class="text-primary-400">WORLD</span>.
                </span>
            </a>
            <!-- Mobile menu button -->
            <div class="md:hidden">
                <button 
                    type="button" 
                    class="text-white hover:bg-white hover:bg-opacity-10 p-2 rounded-md"
                    on:click={() => mobileMenuOpen = !mobileMenuOpen}
                >
                    <i class="fa-solid fa-bars"></i>
                      <IconMenu2 />
                </button>
            </div>

            <!-- Desktop menu -->
            <div class="hidden md:flex gap-5">
                <a href="/" class="text-white py-2 px-4 hover:bg-white hover:bg-white/10 transition-all duration-150 rounded-md">Home</a>
                <a href="#" class="text-white py-2 px-4 hover:bg-white hover:bg-white/10 transition-all duration-150 rounded-md">Courses</a>
            </div>
        </div>
    </div>

    <!-- Mobile menu panel -->
    {#if mobileMenuOpen}
        <div class="md:hidden" id="mobileMenu">
            <div class="px-2 pt-2 pb-3 space-y-1">
                <a href="/" class="text-white block px-3 py-2 rounded-md hover:bg-white hover:bg-white/10">Home</a>
                <a href="#" class="text-white block px-3 py-2 rounded-md hover:bg-white hover:bg-white/10">Courses</a>
            </div>
        </div>
    {/if}
</nav>
