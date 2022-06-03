<script>
  import "./assets/css/style.css";
  let count = 0;
  let countArray = [];

  const handleClick = () => {
    count++;
    countArray = [...countArray, count];
  };
  $: double = count * 2;
  $: if (count > 10) {
    console.log("okok👍");
  }
  $: sum = countArray.reduce((acc, current) => acc + current, 0);
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
    class="mt-6 mx-8 shadow-md rounded-md flex justify-center bg-white overflow-hidden"
  >
    <img src="/logo.png" alt="logo" class="w-16 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded p-8">
    <!-- CONTENU ICI -->
    <h1 class=" text-2xl mb-8">How mamy clicks can you do ?</h1>
    <p>{count}</p>
    <p>Double : {double}</p>
    <p>{sum}</p>
    <button
      class=" px-3 py-2 bg-amber-600 rounded textwh"
      on:click={handleClick}>Click me 👌</button
    >
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
