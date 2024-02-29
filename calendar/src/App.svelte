<script>
  import Calendar from "./lib/calendar.svelte";
  import data from "../data.mjs";
  import Scroller from "./lib/scroller.svelte";
  let screenSize = window.innerWidth;
</script>

<main>
  {#if screenSize > 725}
    <Calendar
      dayOfFirst={data.dayOfFirst}
      numDays={data.numDays}
      month={data.month}
    />
  {:else}
    <Scroller month={data.month} />
  {/if}
</main>

<style>
</style>
