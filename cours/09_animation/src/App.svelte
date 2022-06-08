<script>
  import "./assets/css/style.css";
  import { fly, fade } from "svelte/transition";

  let name = "";
  let deathList = [];
  const killEvent = () => {
    deathList = [...deathList, name];
    name = "";
  };
  $: disabled = name.length > 3 ? false : true;
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
    class="mt-6 mx-8 shadow-md rounded-md flex justify-center bg-white overflow-hidden"
  >
    <img src="/logo.png" alt="logo" class="w-16 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded-md p-8">
    <!-- CONTENU ICI -->
    <h1 class=" title primary">Death note</h1>
    <form class=" my-4 shadow-sm p-8" on:submit|preventDefault={killEvent}>
      <div class="form-control input">
        <label for="name">Ajouter le nom de quelqu'un</label>
        <input type="text" name="name" bind:value={name} />
      </div>
      <button type="submit" class="btn primary mt-4" {disabled}>Ajouter</button>
    </form>
    <div class=" bg-black text-white rounded-md shadow-md p-8">
      {#each deathList as death}
        <p
          class="mt-2 text-xl text-center"
          in:fly={{ y: 200, duration: 1000 }}
          out:fade
        >
          {death}
        </p>
      {:else}
        <p class="text-3xl text-center">No one to kill</p>
      {/each}
      {#if deathList.length}
        <button
          class="btn cancel mt-8 mx-auto block"
          on:click={() => (deathList = [])}>Remove All</button
        >
      {/if}
    </div>
  </main>
</div>

<style>
  .animation-image {
    @apply cursor-pointer duration-200;
  }

  .animation-image:hover {
    @apply scale-75;
  }
</style>
