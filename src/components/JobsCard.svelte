<script>
  import PocketBase from "pocketbase";
  import { onMount } from "svelte";

  let note;
  let headline;

  let load = async function () {
    const pb = new PocketBase("https://ily39d9iu6o63l8.pocketbase.tech");
    let result = await pb.collection("notes").getOne("8tr9q6jkly3ftre");

    headline = result.title;
    note = result.content;
  };

  onMount(function () {
    load();
  });
</script>

<section class="jobs mt-6">
  <ul>
    <li
      class="w-full px-2 py-2 border border-red-500 border-dashed text-black bg-white"
    >
      <h2 class="font-bold text-lg block text-center">{headline}</h2>
      <div class="block text-center text-sm">{@html note}</div>
    </li>
  </ul>
</section>
