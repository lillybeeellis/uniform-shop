<script>
  /* each garment is defined as a variable.
   * let is a boolean variable
   */
  //let tShirt = false;
  //let sportsfit = false;
  // let longsleeved = false;
  //let jumpers = false;
  //let shoes = false;
  //let socks = false;
  //let swimmingcap = false;
  //let sunhat = false;

  // import { stores } from "@sapper/app";
  // const { session } = stores();

  // //alowing saved items in the options from multiple pages
  // function addOptions() {
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
    { name: "Rangi Ruru PE top - $ 68.00", ticked: false, size: "Size" },
    { name: "Rangi Ruru PE shorts - $ 30.00", ticked: false, size: "Size" },
    {
      name: "Rangi Ruru track pants - $ 73.10 - $ 85.90 (Optional)",
      ticked: false,
      size: "Size"
    },
    { name: "PE Bag - $ 50.00 (Optional)", ticked: false, size: "Size" },
    { name: "Rugby jersey - $ 92.00", ticked: false, size: "Size" },
    { name: "Sports socks - $ 10.75", ticked: false, size: "Size" },
    { name: "Swimming cap - $ 7.00", ticked: false, size: "Size" },
    { name: "Hoodie -  $ 130.00", ticked: false, size: "Size" }
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

  #sportsuni {
    height: 300px;
    width: 300px;
    float: right;
  }

  #optionsbutton {
    margin: right;
    display: block;
  }
  #items {
    margin: right;
  }

  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      " banner                           banner   " auto
      " uniform                        uniform    " auto
      " items                        sportsuni " auto
      " items                        . " auto
      " items                         .   " auto
      " items                       .             " auto
      "  optionsbutton              .      " auto
      / auto auto;
  }
  #sportsuni {
    grid-area: sportsuni;
  }

  #optionsbutton {
    grid-area: optionsbutton;
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

<!---this css is styling the website, adding images, colour, banners etc.-->
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
  <figure id="sportsuni">
    <img
      src="/images/sportsuni.png"
      alt="sportsuni"
      title="Image courtesy to Rangi Ruru" />

  </figure>
  <div id="items">
    <h2 class="title is-2">SPORTS UNIFORM:</h2>
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
