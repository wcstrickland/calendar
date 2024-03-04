<script>
  export let month;
  export let currentMonth;
  import EventCard from "./eventCard.svelte";
  let days = [];
  let today = new Date();

  for (let i = 1; i <= month.numDays; i++) {
    days.push(i);
  }

  let dayMap = {
    "0": "Monday",
    "1": "Tuesday",
    "2": "Wednesday",
    "3": "Thursday",
    "4": "Friday",
    "5": "Saturday",
    "6": "Sunday",
  };

  function getDayOfWeek(date, monthStartDay) {
    return dayMap[(date - monthStartDay + 7) % 7];
  }
</script>

<div style="display:flex; flex-direction:column">
  {#each days as day, i}
    {#if i >= today.getDate() || !currentMonth}
      {#if month[day][0]["title"] !== "" && month[day][0]["title"] !== undefined}
        <h1>{getDayOfWeek(day, month.dayOfFirst)} {month.month} {day}</h1>
      {:else}
        <div style="margin-top:.5em;"></div>
      {/if}
      {#each month[day] as event}
        {#if event["title"] !== "" && event["title"] !== undefined}
          <EventCard data={event} />
        {/if}
      {/each}
    {/if}
  {/each}
</div>

<style>
</style>
