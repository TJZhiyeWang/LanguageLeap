<!-- Content.svelte -->
<script lang="ts">
    import Interface from "./Interface.svelte";
  let current = "home";
</script>

{#if current == "home"}
  <div class="nav">
    <div class="nav-card" on:click={() => current="food"}>
      <img src="/images/Food.jpg" alt="Food Image" />
      <span>Food</span>
    </div>

    <div class="nav-card" on:click={() => current="conversation"}>
      <img src="/images/conversation.jpg" alt="Conversation Image" />
      <span>Conversation</span>
    </div>
  </div>
{:else}
  <Interface bind:current></Interface>
{/if}

<style>
  .nav {
    display: flex;
  }

  .nav-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    flex: 1;
    padding: 1rem;
    margin: 1rem;
    /* border: 1px solid #ccc; */
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .nav-card:active {
    background-color: #f0f0f0;
  }

  .nav-card:hover {
    background-color: #f0f0f0;
  }

  .nav-card img {
    max-width: 100%;
    height: auto;
    border-radius: 50%;
    /* margin-bottom: 0.5rem; */
  }
</style>
