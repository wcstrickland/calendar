<script>
  import Calendar from "./lib/calendar.svelte";
  import currentMonth from "../currentMonth.mjs";
  import nextMonth from "../nextMonth.mjs";
  import Scroller from "./lib/scroller.svelte";
  let screenSize = window.innerWidth;
</script>

<main>
  {#if screenSize > 725}
    <Calendar
      useMonth={currentMonth}
      dayOfFirst={currentMonth.dayOfFirst}
      numDays={currentMonth.numDays}
      month={currentMonth.month}
      currentMonth={true}
    />
    <Calendar
      useMonth={nextMonth}
      dayOfFirst={nextMonth.dayOfFirst}
      numDays={nextMonth.numDays}
      month={nextMonth.month}
      currentMonth={false}
    />
  {:else}
    <Scroller currentMonth={true} month={currentMonth} />
    <Scroller currentMonth={false} month={nextMonth} />
  {/if}
</main>

<style>
</style>
