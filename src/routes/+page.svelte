<script>
  import MondayGrid from "../components/MondayGrid.svelte";
  import TuesdayGrid from "../components/TuesdayGrid.svelte";
  import WednesdayGrid from "../components/WednesdayGrid.svelte";
  import ThursdayGrid from "../components/ThursdayGrid.svelte";
  import FridayGrid from "../components/FridayGrid.svelte";
  import SaturdayGrid from "../components/SaturdayGrid.svelte";
  import SaleGrid from "../components/SaleGrid.svelte";
  import WelcomeCard from "../components/WelcomeCard.svelte";
  import ImageCard from "../components/ImageCard.svelte";
  import HeadlineSection from "../components/HeadlineSection.svelte";
</script>

<div class="grid grid-cols-6 gap-3">
  <div class="col-span-6 md:col-span-3">
    <ImageCard />
    <WelcomeCard />
    <HeadlineSection />
    <MondayGrid />
    <TuesdayGrid />
    <WednesdayGrid />
  </div>
  <div class="col-span-6 md:col-span-3">
    <img
      src="https://avatars.githubusercontent.com/u/20771653?v=4"
      alt=""
      class="w-20 rounded-full mx-auto mt-6"
    />
    <h2 class="mt-3 mb-3 font-bold text-lg text-center">Karl Heinz Klotz</h2>
    <p class="text-center">
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Enim
      exercitationem sunt aut eveniet velit quaerat omnis iure. Deleniti,
      praesentium quidem modi rerum adipisci voluptatem deserunt quod? Impedit
      voluptatibus ipsam totam.
    </p>
    <ThursdayGrid />
    <SaleGrid />
    <FridayGrid />
    <SaturdayGrid />
  </div>
</div>
