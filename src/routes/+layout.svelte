<script>
  import "../app.css";
  import Nav from './Nav.svelte';
  import { fly } from 'svelte/transition'
  import { cubicIn, cubicOut } from 'svelte/easing';

  export let data
</script>

<Nav />

{#key data.url}
    <main class="flex justify-center"
        in:fly={{ easing: cubicOut, y: 10, duration: 200, delay: 400 }}
        out:fly={{ easing: cubicIn, y: -10, duration: 200 }}
    >
        <slot />
    </main>
{/key}

