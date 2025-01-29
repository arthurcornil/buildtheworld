<script lang="ts">
    let { isOpen = $bindable() } = $props();

    function closeModal() {
        isOpen = false;
    }
</script>
{#if isOpen}
  <div
    class="fixed inset-0 bg-black/80 flex items-center justify-center"
    on:click={closeModal}
    role="presentation"
  >
    <div
      class="bg-white rounded-xl p-7 mx-5 w-2xl max-w-screen"
      on:click|stopPropagation
      role="dialog"
      aria-modal="true"
    >
        <slot />
    </div>
  </div>
{/if}
