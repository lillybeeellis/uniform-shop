<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  function removeItem(index) {
    session.garments = [
      ...session.garments.slice(0, index),
      ...session.garments.slice(index + 1)
    ];
  }

  function saveDataToLocal() {
    // let data = JSON.stringify(session.garments)
    // localStorage.setItem('session.garments', data)
    let orders = {
      name: session.name,
      garments: session.garments
    };
    console.log("Starting save...");
    console.log(session.name);
    console.log(session.garments);
    db.collection("orders")
      .doc(session.name)
      .set(orders);
  }

  async function getDataFromLocal() {
    // let data = localStorage.getItem('session.garments')
    // session.garments = JSON.parse(data)

    // get the document from the database for the given name
    console.log(session.name);
    let nameDoc = await db.collection("orders").doc(session.name).get();
    let orders = nameDoc.data();
    session.garments = orders.garments
  }
</script>

<style>
  /*#####banner image####*/

  /* ######## LAYOUT #########*/
  #banner {
    height: 250px;
    width: 1500px;
  }

  #grid-container {
    display: grid;
    grid:
      "   banner           banner  " auto
      "      text    text" auto
      / auto auto;
  }

  #text {
    grid-area: text;
  }
  #banner {
    grid-area: banner;
    justify-self: stretch;
  }
  .card {
    margin-top: 15px;
  }
</style>

<div id="grid-container">
  <!---the banner image which is on every page-->

  <img
    id="banner"
    src="/images/banner.png"
    alt="banner"
    title="Image courtesy to Rangi Ruru" />

  <!---the heading 1-->
  <div id="text">
    <h2 class="subtitle is-2">Garments you have selected:</h2>
    <p>{session.name}</p>
  </div>
  <!---button going to the summer and winter year 7-10 uniform page-->

</div>
<!---styling each garment selected using bulma-->
{#if session.garments}
  {#each session.garments as garment, index}
    {#if garment.ticked}
      <div class="card">
        <div class="card-content">
          <div class="media">
            <div class="media-left">
              <p>{garment.name}</p>
            </div>
            <div class="media-content">
              <p>{garment.size}</p>
            </div>
            <!---A remove button-->
            <button
              class="button"
              on:click={() => {
                removeItem(index);
              }}>
              Remove
            </button>
          </div>
        </div>
      </div>
    {/if}
  {/each}
{/if}
<!---order button-->
<button class="button">Order!</button>
<!---Remember me button-->
<button class="button" on:click={saveDataToLocal}>Remember me</button>
<!---Get my details button-->
<button class="button" on:click={getDataFromLocal}>Get my details</button>
