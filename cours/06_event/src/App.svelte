<script>
  import "./assets/css/style.css";
  import ImageDetails from "./ImageDetails.svelte";

  let scale = 1;
  const handleWheel = (e) => {
    if (e.deltaY < 0) {
      scale += 0.5;
    } else {
      scale -= 0.5;
    }
  };

  let imageDetails = [
    {
      id: 1,
      src: "https://picsum.photos/2000/3000",
      name: "LittleBig.png",
      size: "3.8MB",
    },
    {
      id: 2,
      src: "https://picsum.photos/2010/3000",
      name: "DestinyChild.png",
      size: "1.0MB",
    },
    {
      id: 3,
      src: "https://picsum.photos/2020/3000",
      name: "bigDuck.heic",
    },
    {
      id: 4,
      src: "https://picsum.photos/2030/3000",
      name: "interstellar-385421555.png",
      size: "1.2GB",
    },
  ];
  const handleDelete = (e) => {
    console.log(e);
    console.log(e.detail);
    imageDetails = imageDetails.filter((img) => img.id != e.detail);
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
    <p
      style="transform:scale({scale})"
      class=" text-center"
      on:wheel={handleWheel}
    >
      Ceci est le pain de TPK
    </p>
    <button
      class=" m-8 p-2 bg-red-600 text-white"
      on:click|once={() => alert("test alert")}>Alert</button
    >
    <ul class=" grid grid-cols-2 gap-x-4 gap-y-8 mt-8 lg:grid-cols-4">
      {#each imageDetails as detail}
        <ImageDetails {...detail} on:deleteImg={handleDelete} />{/each}
    </ul>
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
