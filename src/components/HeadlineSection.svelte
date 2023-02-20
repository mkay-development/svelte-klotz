<script>
	import PocketBase from 'pocketbase'
  import { onMount } from 'svelte';

  let note;
  let headline;

  let load = async function(){
    const pb = new PocketBase('https://ily39d9iu6o63l8.pocketbase.tech');
    let result = await pb.collection('notes').getOne('5pdjciqz2fxg181');

    headline = result.title;
    note = result.content;
  }

  onMount(function(){
load();
  });
</script>

<h1 class="text-lg font-bold block text-center mt-6 text-white">
  {headline}
</h1>
<p class="text-red-400 text-center text-sm">{@html note}</p>
