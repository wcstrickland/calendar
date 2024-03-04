<script>
  import Row from "./row.svelte";
  import Header from "./header.svelte";
  export let currentMonth;
  export let useMonth;
  export let month;
  export let dayOfFirst;
  export let numDays;
  let counter = 1;
  let week1 = [];
  let week2 = [];
  let week3 = [];
  let week4 = [];
  let week5 = [];
  let week6 = [];
  let weeks = [week2, week3, week4, week5, week6];

  // week 1
  for (let i = 0; i < dayOfFirst; i++) {
    week1.push("x");
  }
  for (let i = dayOfFirst; i < 7; i++) {
    week1.push(counter);
    counter += 1;
  }

  for (const week of weeks) {
    for (let i = 0; i < 7; i++) {
      if (counter <= numDays) {
        week.push(counter);
        counter += 1;
      } else {
        week.push("x");
      }
    }
  }
  weeks = [week1, week2, week3, week4, week5, week6];
</script>

<div style="display: flex; justify-content:center;">
  <h1>{month}</h1>
</div>
<div
  style="display: flex; flex-direction:column; justify-content:space-evenly;"
>
  <Header />
  {#each weeks as week }
    <Row currentMonth={currentMonth} useMonth={useMonth} days={week}/>
  {/each}
</div>

<style>
</style>
