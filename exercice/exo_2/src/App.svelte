<script>
  import "./assets/css/style.css";
  import DropDown from "./DropDown.svelte";

  let countries = [
    {
      id: 1,
      src: "https://countryflagsapi.com/png/be",
      country: "Belgium",
    },
    {
      id: 2,
      src: "https://countryflagsapi.com/png/it",
      country: "Italy",
    },
    {
      id: 3,
      src: "https://countryflagsapi.com/png/fr",
      country: "France",
    },
    {
      id: 4,
      src: "https://countryflagsapi.com/png/ga",
      country: "Gabon",
    },
    {
      id: 5,
      src: "https://countryflagsapi.com/png/us",
      country: "United State",
    },
    {
      id: 6,
      src: "https://countryflagsapi.com/png/sr",
      country: "Suriname",
    },
  ];
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
    class="mt-6 mx-8 shadow-md rounded-md flex justify-center bg-white overflow-hidden"
  >
    <img src="/logo.png" alt="logo" class="w-16 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded p-8">
    <!-- CONTENU ICI -->
    <DropDown tabCountries={countries} />
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
