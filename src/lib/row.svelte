<script>
    import Cell from "./cell.svelte";
    export let days;
    export let useMonth;
    export let currentMonth;

</script>

<div id="header" style="display: flex;justify-content:space-evenly">
    {#each days as day }
        <Cell currentMonth={currentMonth} useMonth={useMonth} label={day}/>
    {/each}

</div>

<style>
    div{
        display: flex;
        flex-direction: row;
    }

    #header{
        width: 80vw;
        margin: .5em 0 .5em 0;
    }
</style>