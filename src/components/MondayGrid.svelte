<script>
  import { onMount } from "svelte";

  let items = [];

  let load = function () {
    fetch("https://catalog.klotz-imbiss.de/api/card?populate=montag")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        items = data.data.attributes.montag.data;
      });
  };

  onMount(function () {
    load();
  });
</script>
<h2 class="mt-6 mb-3 text-white font-bold">Montag</h2>
<div class="border border-black">
  <div class="grid grid-cols-12 text-white bg-[#5C7987] px-2 py-2">
    <div class="col-span-12 md:col-span-8">Name</div>
    <div class="col-span-12 md:col-span-4">Preis</div>
  </div>

  {#each items as item}
    <div class="grid grid-cols-12 px-2 py-2 bg-[#5C7987]">
      <div class="col-span-12 md:col-span-8">{item.attributes.name}</div>
      <div class="col-span-12 md:col-span-4">{item.attributes.price} €</div>
    </div>
  {/each}
</div>