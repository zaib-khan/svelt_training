<script>
  import "./assets/css/style.css";
  import GenerateurDeBlague from "./GenerateurDeBlague.svelte";
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
  class="mt-6 mx-8 flex justify-center "
  >
    <img src="img/OK.gif" alt="logo" class="w-32 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded p-8 
  flex justify-center">
    <!-- CONTENU ICI -->
    <GenerateurDeBlague />
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
