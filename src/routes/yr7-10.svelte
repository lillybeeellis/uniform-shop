<script>
  /* each garment is defined as a variable.
   * let is a boolean variable
   */
  /*
  let summerdress = false;
  let culottes = false;
  let longsleeved = false;
  let jerseys = false;
  let blazer = false;
  let rangisocks = false;
  let shoes = false;
  let jacket = false;

  let kilt = false;
  let culottes2 = false;
  let lightshirt = false;
  let tie = false;
  let jersey2 = false;
  let blazer2 = false;
  let tights = false;
  let shoes2 = false;
  let jacket2 = false;
  */
  // import { stores } from "@sapper/app";
  // const { session } = stores();

  // console.log("Working on junior");
  // //alowing saved items in the options from multiple pages
  // function addOptions() {
  //   console.log("Added item");
  //   session.garments = [...session.garments, ...options];
  // }
  // each object has a name and a Boolean
  //variable for each singular garment that is not selected
  let notTicked = false;

  import { stores } from "@sapper/app";
  const { session } = stores();

  if (session.garments === undefined) {
    session.garments = [];
  }

  //alowing saved items in the options from multiple pages
  function addOptions() {
    // session.garments = [...session.garments, ...options];
    //if user does not eneter name or too long or too short it will alert them
    options.forEach(function addOptions(item, index) {
      if (false === item.ticked) {
        console.log(session.garments === false);
        notTicked = false;
      } else {
        // for each loop to go through the options array
        // if the option is ticked, then add it to garments
        options.forEach(function addOptions(item, index) {
          if (true === item.ticked) {
            console.log(session.garments === true);
            session.garments = [...session.garments, item];
          }
        });
      }
    });
    if (false === notTicked) alert(`You did not save any garments`);
  }

  // array of garments
  let options = [
    {
      name: "Summerdress - $ 130.00",
      ticked: false,
      size: "Size"
    },
    { name: "Culottes - $ 79.50 (Optional)", ticked: false, size: "Size" },
    { name: "Short sleeved blouse $ 68.50 ", ticked: false, size: "Size" },

    { name: "Navy blazer - $ 299.00", ticked: false, size: "Size" },
    {
      name: "Rangisocks - $ 8.00",
      ticked: false,
      size: "Size"
    },

    {
      name: "RR navy or yellow waterproof jacket - $ 140.00 (Optional)",
      ticked: false,
      size: "Size"
    },
    {
      name: "Winter kilt $ 250.00",
      ticked: false,
      size: "Size"
    },
    { name: "Blue culottes - $ 79.50 (Optional)", ticked: false, size: "Size" },
    {
      name: "RR blue Winter blouse - $ 63.70 - $ 67.20",
      ticked: false,
      size: "Size"
    },
    { name: "Navy tie - $ 34.40", ticked: false, size: "Size" },
    {
      name: "Navy cardigan - $ 90.00 - $ 103.00",
      ticked: false,
      size: "Size"
    },

    {
      name: "Navy tights or navy over the knee socks - $ 18.40",
      ticked: false,
      size: "Size"
    },
    {
      name: "RR navy or yellow waterproof jacket $ 140.00 (Optional)",
      ticked: false,
      size: "Size"
    }
  ];
</script>

<style>
  button {
    display: block;
  }
  /*#####banner image####*/
  #banner {
    height: 250px;
    width: 1500px;
  }

  #uniform {
    height: 37px;
    width: 250px;
  }

  #summerjun {
    height: 300px;
    width: 300px;
  }

  #winter {
    height: 300px;
    width: 300px;
  }

  #optionsbutton {
    margin: left;
    display: block;
  }

  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      " banner                           banner   " auto
      " uniform                        uniform    " auto
      " items                        winter  " auto
      " items                        summerjun " auto
      "  items                         .   " auto
      " items                       .             " auto
      "  optionsbutton              .      " auto
      / auto auto;
  }

  #summerjun {
    grid-area: summerjun;
  }
  #winter {
    grid-area: winter;
  }
  #optionsbutton {
    grid-area: optionsbutton;
    display: block;
  }

  #items {
    grid-area: items;
  }
  #uniform {
    grid-area: uniform;
    place-self: center;
  }
  #banner {
    grid-area: banner;
    justify-self: stretch;
  }
</style>

<!---this code is adding the banner which is on every page.-->
<div id="grid-container">

  <img
    id="banner"
    src="/images/banner.png"
    alt="banner"
    title="Image courtesy to Rangi Ruru" />

  <!---this code is adding the uniform image under the banner which is on every page.-->
  <figure id="uniform">
    <img
      src="/images/uniform.png"
      alt="uniform"
      title="Image courtesy to Rangi Ruru" />
  </figure>
  <!---images which show the user what the uniform looks like. These images are from Rangiruru.-->
  <figure id="summerjun">
    <img
      src="/images/summerjun.png"
      alt="summerjun"
      title="Image courtesy to Rangi Ruru" />
  </figure>

  <figure id="winter">
    <img
      src="/images/winter.png"
      alt="winter"
      title="Image courtesy to Rangi Ruru" />
  </figure>

  <div id="items">
    <h2 class="title is-2">JUNIOR UNIFORM:</h2>
    <ul>
      <!-- loop through the array -->
      {#each options as option}
        <!-- add a labelled checkbox for each one -->
        <label>
          <li>
            <!-- the tickbox is linked to the Boolean -->
            <input type="checkbox" bind:checked={option.ticked} />

            <!--different sizing of garments-->
            <select bind:value={option.size}>
              <option>size</option>
              <option value="4">4</option>
              <option value="6">6</option>
              <option value="8">8</option>
              <option value="10">10</option>
              <option value="12">12</option>
              <option value="14">14</option>
              <option value="16">16</option>
            </select>
            <!-- the item for the tickbox -->
            {option.name}
          </li>
        </label>
      {/each}
    </ul>
  </div>
  <!--Multiple buttons including a save button, checkout and back to options-->
  <div id="optionsbutton">
    <button class="button is-focused" on:click={addOptions}>save items</button>
    <a class="button" href="options" style="margin:5px;">options</a>
    <br />
    <a class="button" href="checkout" style="margin:5px;">checkout</a>

  </div>

</div>
