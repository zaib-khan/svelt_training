<script>
  let blague;
  let reponse;

  setTimeout(async () => {
    const res = await fetch("https://www.blagues-api.fr/api/random", {
      headers: {
        Authorization: `Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiMzUzMjcwMTg1MzU4MDAwMTI4IiwibGltaXQiOjEwMCwia2V5IjoiZEZ3c1BmU3pmM0NmSXFxZm5QWUxpMVNQOGZZU1M4YlZ5M0V5N1liV3JZcWFBNWdIUEQiLCJjcmVhdGVkX2F0IjoiMjAyMi0wNi0wOFQxMjowNDowOSswMDowMCIsImlhdCI6MTY1NDY4OTg0OX0.iRkwYnM-IBhIFn9euywlt0vOIPuT-Xu15sZZWXrYJZ4`,
      },
    });
    let temp = await res.json();
    blague = temp.joke;
    reponse = temp.answer;
  }, 2000);

  const nouvelleBlague = () => {
    blague = "";
    setTimeout(async () => {
      const res = await fetch("https://www.blagues-api.fr/api/random", {
        headers: {
          Authorization: `Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoiMzUzMjcwMTg1MzU4MDAwMTI4IiwibGltaXQiOjEwMCwia2V5IjoiZEZ3c1BmU3pmM0NmSXFxZm5QWUxpMVNQOGZZU1M4YlZ5M0V5N1liV3JZcWFBNWdIUEQiLCJjcmVhdGVkX2F0IjoiMjAyMi0wNi0wOFQxMjowNDowOSswMDowMCIsImlhdCI6MTY1NDY4OTg0OX0.iRkwYnM-IBhIFn9euywlt0vOIPuT-Xu15sZZWXrYJZ4`,
        },
      });
      let temp = await res.json();
      blague = temp.joke;
      reponse = temp.answer;
    }, 2000);
  };
</script>

{#if blague}
  <div class="flex flex-col">
    <p class="">{blague}</p>
    <p>{reponse}</p>
    <button class="btn cancel mt-8 mx-auto block" on:click={nouvelleBlague}
    >Une autre blague</button>
  </div>

  
{:else}
  <div class="flex items-center">
    <img src="img/1474.gif" alt="" />
    <p>Recherche de blague 👌</p>
  </div>
{/if}
