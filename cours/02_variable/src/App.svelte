<script>
  import "./assets/css/style.css";
  let name = "Bernard";
  let src = 'https://file1.closermag.fr/var/closermag/storage/images/media/images-des-contenus/closer-v1/suite/george-clooney-sans-dents/1051249-2-fre-FR/George-Clooney-sans-dents.jpg?alias=original';
  let classe = `${name === "Bernard"?'w-64':'w-4'}`;
</script>

<div class="bg-slate-50 flex flex-col min-h-screen">
  <header
    class="mt-6 mx-8 shadow-md rounded-md flex justify-center bg-white overflow-hidden"
  >
    <img src="/logo.png" alt="logo" class="w-28 animation-image" />
  </header>
  <main class="container mx-auto m-8 border-2 border-dashed rounded p-8">
    <!-- CONTENU ICI -->
    Votre contenu ici !
    Hello {name +' lompia'}
    <img {src} class={classe} alt="sans dents">
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
