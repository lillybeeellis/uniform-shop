<style>
  /*#####banner image####*/
  #banner {
    height: 250px;
    width: 2200px;
    margin-left: 15%;
  }

  #uniform {
    height: 37px;
    width: 250px;
    margin-left: 41%;
  }
  div {
    margin-left: 110px;
  }

  h2 {
    margin-left: 210px;
  }

  #winter {
    height: 300px;
    width: 300px;
  
  }

  #summerjun {
    height: 300px;
    width: 300px;
    
  }

  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      " text winter    " auto
      " text summerjun " auto
      / auto auto;
  }

  #text {
    grid-area: text;
  }
  #winter {
    grid-area: winter;
  }
  #summerjun {
    grid-area: summerjun;
  }
</style>

<figure id="banner">
  <img
    src="/images/banner.png"
    alt="banner"
    title="Image courtesy to Rangi Ruru" />
</figure>

<figure id="uniform">
  <img
    src="/images/uniform.png"
    alt="uniform"
    title="Image courtesy to Rangi Ruru" />
</figure>
<div id="grid-container">

  <div id="text">
    <p>
      <u>
        <h2 class="subtitle is-2">Summer Uniform:</h2>
      </u>
      <li>Summer dress (length to be on the knee)</li>
      <li>Blue culottes (optional)</li>
      <li>RR blue short sleeved shirt (optional)</li>
      <li>Navy cardigan or v-necked jersey</li>
      <li>Navy blazer</li>
      <li>
        White socks, short, with or without RR gold logo (optional with sandals
        but compulsory with lace-up shoes)
      </li>
      <li>
        Brown leather t-bar or u-bar sandals or Brown leather lace-up shoes
      </li>
      <li>RR navy or yellow waterproof jacket (optional)</li>

      <u>
        <h2 class="subtitle is-2">Winter Uniform:</h2>
      </u>
      <li>
        Kilt (length – midway between ankle and knee) or skirt (length to be
        just below the knee)
      </li>
      <li>Blue culottes (optional)</li>
      <li>RR light blue long-sleeved shirt (optional)</li>
      <li>Navy tie</li>
      <li>Navy cardigan or v-necked jersey</li>
      <li>Navy blazer</li>
      <li>Navy tights or navy over the knee socks</li>
      <li>
        Brown leather t-bar or u-bar sandals or brown leather lace-up shoes
      </li>
      <li>RR navy or yellow waterproof jacket (optional)</li>

    </p>
  </div>

  <figure id="winter">
    <img
      src="/images/winter.png"
      alt="winter"
      title="Image courtesy to Rangi Ruru" />
  </figure>

  <figure id="summerjun">
    <img
      src="/images/summerjun.png"
      alt="summerjun"
      title="Image courtesy to Rangi Ruru" />
  </figure>
</div>
