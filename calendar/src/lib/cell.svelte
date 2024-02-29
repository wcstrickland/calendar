<script>
  export let label;
  import data from "../../data.mjs";
  let events = data[label];
  let multi = events.length > 1;
</script>

<div id="cell" style="display: flex; flex-direction:row;">
  <span style="margin-left:5px;">{label}</span>
  <!-- <div> -->
  {#each events as event}
    {#if event["link"] !== undefined && event["link"] !== ""}
      <a href={event["link"]} target="_blank">
        <img
          alt="alt-text"
          style="max-width: 80%; max-height:80%;margin-top:.5em;"
          src={event["img"]}
        />
      </a>
    {/if}
  {/each}
  <!-- </div> -->
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
