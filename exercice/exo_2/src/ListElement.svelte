<script>
  import { createEventDispatcher } from "svelte";
  export let countryName;
  export let countryImg;
  export let updatePlaceholder;
  const dispatch = createEventDispatcher();

  const monTest = () => {
    dispatch("updateTest", { countryImg, countryName });
  };
</script>

<div
  class="flex justify-between p-2 hover:bg-slate-400 duration-100 cursor-pointer"
  on:click={monTest}
>
  <img
    class="w-4 h-4"
    src={countryImg}
    alt="Image du drapeau de {countryName}"
  />
  <span>{countryName}</span>
</div>
