<script>
  export let isPromo = false;
  export let showModal = false;
</script>

<!-- 
Event modifiers

once = makes sure the event can only fire once (remover handler)
preventDefault = prevent the default action (run e.preventDefault())
self = only fires the event if the clicked element is the target 

more events in https://svelte.dev/tutorial/event-modifiers
-->
{#if showModal}
  <div class="backdrop" class:promo={isPromo} on:click|self>
    <div class="modal">
      <slot name="title" />
      <slot />
    </div>
  </div>
{/if}

<style>
  .promo .modal {
    background-color: crimson;
    color: white;
  }

  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.8);
  }

  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background: white;
  }
</style>
