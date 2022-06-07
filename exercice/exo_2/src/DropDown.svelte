<script>
  import ListElement from "./ListElement.svelte";

  export let tabCountries = [];
  let isOpened = false;
  const dropDownClickEvent = () => {
    isOpened = !isOpened;
  };
  const updatePlaceholder = (newPlaceHolder) => {
    placeholder = newPlaceHolder;
  };
  $: placeholder = "Choose a country";

  const test_1 = (e) => {
    console.log(e.detail);
  };
</script>

<div class="relative inline-block text-left">
  <div>
    <button
      type="button"
      class="inline-flex justify-center w-full rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 focus:outline-none"
      on:click={dropDownClickEvent}
    >
      {placeholder}
      <svg
        class="-mr-1 ml-2 h-5 w-5"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 20 20"
        fill="currentColor"
      >
        <path
          fill-rule="evenodd"
          d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
          clip-rule="evenodd"
        />
      </svg>
    </button>
  </div>
  <div
    class="origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 focus:outline-none"
  >
    {#if isOpened}
      {#each tabCountries as country}
        <ListElement
          countryName={country.country}
          countryImg={country.src}
          {updatePlaceholder}
          on:updateTest={test_1}
        />
      {/each}
    {/if}
  </div>
</div>
