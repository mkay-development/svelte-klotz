<script>
  import PocketBase from "pocketbase";
  import { onMount } from "svelte";
  import { url } from "../stores/backend";

  let note;
  let headline;
  let result;
  let items = [];

  let load = async function () {
    const pb = new PocketBase($url);
    result = await pb.collection("notes").getList(1,10);
    items = result.items;
  };

  onMount(function () {
    load();
  });
</script>

<section class="jobs mt-6">
  <ul>
    {#if items}
      {#each items as item}
        <li
          class="w-full px-2 py-2 border border-red-500 border-dashed text-black bg-white"
        >
          <h2 class="font-bold text-lg block text-center">{item.title}</h2>
          <div class="block text-center text-sm">{@html item.content}</div>
        </li>
      {/each}
    {/if}
  </ul>
</section>
