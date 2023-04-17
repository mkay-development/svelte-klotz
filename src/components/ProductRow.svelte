<script>
  export let identifier;
  import PocketBase from "pocketbase";
  import { onMount } from "svelte";
  import { url } from "../stores/backend";

  let item = {};

  let load = async function () {
    const pb = new PocketBase($url);
    const result = await pb.collection("product").getOne(identifier);
    item = result;
  };

  onMount(function () {
    load();
  });
</script>

{#if item.price}
  <div class="col-span-12 md:col-span-8">{item.name}</div>
  <div class="col-span-12 md:col-span-4">{parseFloat(item.price.replace(',', '.')).toFixed(2)} €</div>
{/if}
