<script>
  export let identifier;
  import PocketBase from "pocketbase";
  import { onMount } from "svelte";

  let item =  {};

  let load = async function () {
    const pb = new PocketBase("https://ily39d9iu6o63l8.pocketbase.tech");
    const result = await pb.collection("product").getOne(identifier);
    item = result;
  };

  onMount(function () {
    load();
  });
</script>

<div class="col-span-12 md:col-span-8">{item.name}</div>
<div class="col-span-12 md:col-span-4">{item.price} €</div>
