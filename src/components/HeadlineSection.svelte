<script>
  import { onMount } from "svelte";

  let headline = "";
  let note = "";

  let load = function () {
    fetch("https://catalog.klotz-imbiss.de/api/card")
      .then((response) => {
        return response.json();
      })
      .then((data) => {
        headline = data.data.attributes.headline;
        note = data.data.attributes.note;
      });
  };

  onMount(function () {
    load();
  });
</script>

<h1 class="text-lg font-bold block text-center mt-6 text-white">
  {headline}
</h1>
<p class="text-red-800 text-center">{note}</p>
