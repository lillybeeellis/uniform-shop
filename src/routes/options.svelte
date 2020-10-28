<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  console.log();
  //alowing saved items in the options from multiple pages
  if (session.garments === undefined) {
    session.garments = [];
  }

  // name variable
  let name = "";
  let letters = /^[A-Za-z]+$/;
  // //alowing saved items in the options from multiple pages
  function addName() {
    session.name = name;
    console.log(session.name);
    //if user does not eneter name or too long or too short it will alert them
    if (name === `` || name.length >= 25 || name.length <= 2) {
      alert(`You did not enter your name`);
    } else if (!name.match(letters)) {
      alert("Please enter a name with no numbers");
    }
  }
</script>

<style>
  /*#####unordered list####*/
  div {
    margin-left: 10px;
  }

  /*#####banner image####*/
  #banner {
    height: 250px;
    width: 2000px;
    justify-self: stretch;
  }
  #information {
    margin: 20px;
  }

  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      "banner banner" auto
      ". div information ." auto
      / auto auto;
  }
</style>

<!---code which styles the page, shaping the banner image, heading 1 and the unordered list.-->
<!---the banner image which is on every page-->
<div id="grid-container">
  <img
    id="banner"
    src="/images/banner.png"
    alt="banner"
    title="Image courtesy to Rangi Ruru" />

  <!---the heading 1-->
  <!--input of name-->
  <div class="box">
    <p>Enter name:</p>
    <input type="text" bind:value={name} />
    <button class="button is-focused" on:click={addName}>Save Name</button>
    <h1 class="subtitle is-1">Options</h1>

    <!---button going to the summer and winter year 7-10 uniform page-->
    <div>
      <li>
        <a class="button" href="yr7-10" style="margin:5px;">
          Summer and winter year 7-10 uniform
        </a>
      </li>
      <!---button going to the summer and winter year 11-13 uniform page-->
      <li>
        <a class="button" href="yr11-13" style="margin:5px;">
          Summer and winter year 11-13 uniform
        </a>
      </li>
      <!---button going to the sports uniform page-->
      <li>
        <a class="button" href="sports" style="margin:5px;">Sports uniform</a>
      </li>

      <!---button going to the checkout page-->
      <li>
        <a class="button" href="checkout" style="margin:5px;">Checkout</a>
      </li>

      <figure id="information">
        <h3 class="subtitle is-3">Information</h3>
        <li>41 Hewitts Road</li>
        <li>n.pooley@rangiruru.school.nz</li>
        <li>(03) 983 3785</li>
        <li>
          Shop Hours during Term Time: Tuesday 12.45 – 2.00pm Thursday 12.45 –
          2.00pm Friday 12.55 – 4.00pm
        </li>
        <li>
          Shop Hours Term Holidays 2020 Wednesday 22 July 2020 10.00am – 1.00pm
        </li>
      </figure>
    </div>

  </div>
</div>
