<script>
  import { onMount } from "svelte";

  let items = [];

  let load = function () {
    fetch("https://catalog.klotz-imbiss.de/api/card?populate=samstag")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        items = data.data.attributes.samstag.data;
      });
  };

  onMount(function () {
    load();
  });
</script>


<h2 class="mt-6 mb-3 text-white">Samstag</h2>
<div class="grid grid-cols-12 font-bold bg-gray-400 px-2 py-2">
  <div class="col-span-12 md:col-span-8">Name</div>
  <div class="col-span-12 md:col-span-4">Preis</div>
</div>
{
#each items as item }
  <div class="grid grid-cols-12 bg-white px-2 py-2" >
    <div class="col-span-12 md:col-span-8">{item.attributes.name}</div>
    <div class="col-span-12 md:col-span-4">{item.attributes.price} €</div>
  </div>
{/each}