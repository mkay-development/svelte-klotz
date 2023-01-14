<script>
  import "../tailwind.css";
  import Fa from "svelte-fa";
  import { faHeart } from "@fortawesome/free-solid-svg-icons";
</script>

<header class="mx-auto max-w-5xl my-2 flex justify-between px-2 py-2">
  <h1 class="text-xl font-bold"><a href="/">Grill & Imbiss Klotz</a></h1>
  <div class="nav space-x-3 mt-1 text-white">
    <a href="/impressum">Impressum</a>
  </div>
</header>

<main class="mx-auto max-w-5xl my-2 px-2 py-2"><slot /></main>

<footer class="mx-auto max-w-5xl my-2 mt-6 px-2 py-2">
  <div class="grid grid-cols-6">
    <div class="col-span-6 md:col-span-2">
      <a href="/impressum">Impressum</a> &
      <a href="/data-privacy">Datenschutz</a>
    </div>
    <div class="col-span-6 md:col-span-2 flex">
      Made with <Fa icon={faHeart} class="text-red-400 mt-1 mx-2" /> by Jonathan
    </div>
    <div class="col-span-6 md:col-span-2">
      Copyright by <a
        href="https://www.mkay-development.de"
        class="text-blue-600">MkaY Development</a
      >
    </div>
  </div>
</footer>
