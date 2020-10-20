<script>
  /* each garment is defined as a variable.
   * let is a boolean variable
   */
  // let summerskirt = false;
  // let culottes2 = false;
  // let shortsleeved = false;
  // let jerseys2 = false;
  // let blazer2 = false;
  // let rangisocks = false;
  // let shoes = false;
  // let jacket = false;

  // let kilt = false;
  // let culottes3 = false;
  // let lightshirt = false;
  // let tie = false;
  // let tie13 = false;
  // let blazer = false;
  // let highsocks = false;
  // let shoes3 = false;
  // let jacket2 = false;

  // an array of objects
  // each object has a name and a Boolean

  import { stores } from "@sapper/app";
  const { session } = stores();

  //alowing saved items in the options from multiple pages
  function addOptions() {
    session.garments = [...session.garments, ...options];
  }

  // array of garments
  let options = [
    {
      name:
        "Tartan summer weight skirt (length to be just below the knee) - $ 109.70",
      ticked: false,
      size: "Size"
    },
    { name: "Culottes - $ 79.50 (Optional)", ticked: false, size: "Size" },
    {
      name: "RR white short-sleeved shirt - $ 59.30 - $ 61.00",
      ticked: false,
      size: "Size"
    },
    { name: "Navy cardigan - $ 90.00 - $ 103.00", ticked: false, size: "Size" },

    { name: "Navy blazer - $ 299.00", ticked: false, size: "Size" },
    {
      name: "Rangi socks - $ 8.00",
      ticked: false,
      size: "Size"
    },

    {
      name: "Winter kilt - $ 250.00",
      ticked: false,
      size: "Size"
    },
    { name: "Blue culottes - $ 79.50 (Optional)", ticked: false, size: "Size" },
    { name: "Winter blouse - $ 61.00", ticked: false, size: "Size" },
    {
      name: "Navy/gold striped tie (Year 11-12) - $ 33.60",
      ticked: false,
      size: "Size"
    },
    { name: "Gold tie (Year 13) - $ 33.60", ticked: false, size: "Size" },
    { name: "Navy cardigan - $ 90.00 - $ 103.00", ticked: false, size: "Size" },
    {
      name: "Navy blazer (blue and gold braid for Year 13) - $ 299.00",
      ticked: false,
      size: "Size"
    },
    {
      name: "Navy socks - $ 18.40",
      ticked: false,
      size: "Size"
    },

    {
      name: "RR navy or yellow waterproof jacket - $ 140.00 (Optional)",
      ticked: false,
      size: "Size"
    }
  ];

  // for each loop to go through the options array
  // if the option is ticked, then add it to garments
  options.forEach(function addOptions(item, index) {
    if (true === item.ticked) {
      console.log(session.garments = true)
      session.garments = [...session.garments, item];
    }
  });
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

  #summersin {
    height: 300px;
    width: 300px;
  }

  #wintersin {
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
      " items                        wintersin  " auto
      " items                        summersin  " auto
      "  items                         .   " auto
      " items                       .             " auto
      "  optionsbutton              .      " auto
      / auto auto;
  }

  #summersin {
    grid-area: summersin;
  }
  #wintersin {
    grid-area: wintersin;
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
  <figure id="summersin">
    <img
      src="/images/summersin.png"
      alt="summersin"
      title="Image courtesy to Rangi Ruru" />
  </figure>

  <figure id="wintersin">
    <img
      src="/images/wintersin.png"
      alt="wintersin"
      title="Image courtesy to Rangi Ruru" />
  </figure>

  <div id="items">
    <h2 class="title is-2">SENIOR UNIFORM:</h2>
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
