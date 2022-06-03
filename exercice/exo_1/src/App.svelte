<script>
  import "./assets/css/style.css";
  const tabLegumes = [
    { name: "Aubergine", season: "automne" },
    { name: "Brocoli", season: "automne" },
    { name: "Oignon", season: "automne" },
    { name: "Tomate", season: "automne" },
    { name: "Radis", season: "printemps " },
    { name: "Céleri", season: "printemps" },
    { name: "Carotte", season: "printemps" },
    { name: "Potiron", season: "Hiver" },
    { name: "Poireau", season: "Hiver" },
    { name: "Châtaigne", season: "Hiver" },
  ];

  let isListDisplayed = true;

  const btnClickEventShowList = () => {
    if (!isListDisplayed) isListDisplayed = true;
    console.log(isListDisplayed);
  };
  const btnClickEventShowOneVegetable = () => {
    if (isListDisplayed) isListDisplayed = false;
    console.log(isListDisplayed);
  };
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
    class="mt-6 mx-8 shadow-md rounded-md flex justify-center bg-white overflow-hidden"
  >
    <img src="/logo.png" alt="logo" class="w-16 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded p-8">
    <!-- CONTENU ICI -->
    <div class=" flex justify-between">
      <button
        class=" bg-orange-500 rounded p-2 text-white hover:bg-orange-800 duration-200"
        on:click={btnClickEventShowList}>Show the liste of vegetable</button
      >
      <button
        class=" bg-blue-500 rounded p-2 text-white hover:bg-blue-800 duration-200"
        on:click={btnClickEventShowOneVegetable}>Show me one vegetable</button
      >
    </div>
    {#if isListDisplayed}
        {#each tabLegumes as { isConnect, time }, index}
          <p class=" mt-2 ml-4">
            {index + 1}. {isConnect ? "Connexion" : "Déconnexion"} à {time}
          </p>
        {/each}
      {/if}
    {:else}
      <button
        class=" px-4 py-2 rounded shadow bg-green-600 text-white duration-200 hover:bg-green-900"
        on:click={toggleLogin}>Log in</button
      >
    {/if}
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
