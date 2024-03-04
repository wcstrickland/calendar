<script>
  export let label;
  export let useMonth;
  export let currentMonth;
  let events = useMonth[label];
  let today = new Date();
  console.log(today.getDate())
  let past = (parseInt(label) < today.getDate() ) && currentMonth;
</script>

<div id="cell" style="display: flex; flex-direction:row;position:relative;">
  <span style="margin-left:5px;">{label}</span>
  <!-- <div> -->
  {#each events as event}
    {#if event["link"] !== undefined && event["link"] !== ""}
      <a href={event["link"]} target="_blank">
        <img
          alt={event["title"]}
          style="max-width: 80%; max-height:80%;margin-top:.5em;"
          src={event["img"]}
        />
      </a>
    {/if}
  {/each}
  <!-- </div> -->
  {#if past}
  <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
    <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); font-size: 8em; color: white;">
      X
    </div>
  </div>
  {/if}
</div>

<style>
  #cell {
    min-width: 3em;
    min-height: 3em;
    width: 13em;
    height: 9em;
    border: 1px solid grey;
  }
</style>
