<script>
  let isWarning = true;
  export let showModal;
</script>
	
  {#if showModal}
  <div class="backdrop" on:click|self>
    <div class="modal">
      <slot></slot>
    </div>
    <button on:click>CLOSE</button>
  </div>
	{/if}

<style>
  .backdrop {
    height: 100vh;
    width: 100vw;
    background-color: rgba(128, 128, 128, 0.6);
    position: absolute;
    z-index: 2;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .modal {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 500px;
    height: 300px;
    background-color: antiquewhite;
    border-radius: 20px;
  }
  .warning {
    color: red;
  }
  h2 {
    font-size: 120px;
  }
</style>