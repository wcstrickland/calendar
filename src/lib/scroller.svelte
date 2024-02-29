<script>

export let month;
import Card from "./card.svelte";
import data from "../../data.mjs";
let days = [];

for(let i=1;i<=data.numDays;i++){
    days.push(i)
}

let dayMap = {
  "0" : "Monday",
  "1" : "Tuesday",
  "2" : "Wednesday",
  "3" : "Thursday",
  "4" : "Friday",
  "5" : "Saturday",
  "6" : "Sunday"
}

function getDayOfWeek(date, monthStartDay){
    return dayMap[(date- monthStartDay + 7) % 7]
}
</script>

<div style="display:flex; flex-direction:column">
    {#each days as day}
    {#if data[day][0]["title"]!=="" &&data[day][0]["title"]!==undefined}
        <h4>{getDayOfWeek(day, data.dayOfFirst)}  {month} {day}</h4>
        {:else}
        <div style="margin-top:.5em;"></div>
    {/if}
        {#each data[day] as event}
            {#if event["title"] !== "" && event["title"]  !== undefined}
                <Card  data={event}/> 
            {/if}
        {/each}
    {/each}

</div>

<style>

</style>