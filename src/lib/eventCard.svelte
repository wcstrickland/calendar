<script>
export let data;
</script>

<div class="card">
  <a href={data.img}><img src={data.img} alt="Avatar" style="width:100%" /></a>
  <div class="container">
    <div style="margin-top:.5em;"><b>{data.title}</b></div>
    <div>@ {data.location}</div>
    <a href={data.link}>Details</a>
    <div>Time: {data.time}</div>
  </div>
</div>

<style>
  .card {
    /* Add shadows to create the "card" effect */
    background-color: rgb(230, 230, 230);
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
    margin: .5em 5px 0 5px;
    border-radius: 10px;
  }

  div{
    color: black;
  }

  /* On mouse-over, add a deeper shadow */
  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  }

  /* Add some padding inside the card container */
  .container {
    padding: 2px 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
</style>
