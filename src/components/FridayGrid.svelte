<script>
  import { onMount } from "svelte";
  import PocketBase from "pocketbase";
  import ProductRow from "./ProductRow.svelte";

  let items = [];

  let load = async function () {
    const pb = new PocketBase("https://ily39d9iu6o63l8.pocketbase.tech");
    const result = await pb.collection("friday").getList(1, 50);
    items = result.items;
  };

  onMount(function () {
    load();
  });
</script>

<h2 class="mt-6 mb-3 text-white font-bold">Freitag</h2>
<div class="border border-black">
  <div class="grid grid-cols-12 text-white bg-[#5C7987] px-2 py-2">
    <div class="col-span-12 md:col-span-8">Name</div>
    <div class="col-span-12 md:col-span-4">Preis</div>
  </div>

  {#each items as item}
    <div class="grid grid-cols-12 px-2 py-2 bg-[#5C7987]">
      <ProductRow identifier={item.product} />
    </div>
  {/each}
</div>
