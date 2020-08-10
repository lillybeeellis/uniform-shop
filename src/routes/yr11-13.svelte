<style>
  /*#####banner image####*/
  #banner {
    height: 250px;
    width: 2000px;
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

  #summersin {
    height: 300px;
    width: 300px;
  }

  #wintersin {
    height: 300px;
    width: 300px;
  }

  #yr13winter {
    height: 300px;
    width: 300px;
  }
  h2 {
    margin-left: 210px;
  }


  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      " text wintersin    " auto
      " text summersin " auto
      " text yr13winter " auto
      / auto auto;
  }

  #text {
    grid-area: text;
  }
  #summersin {
    grid-area: summersin;
  }
  #wintersin {
    grid-area: wintersin;
  }
   #yr13winter {
    grid-area: yr13winter;
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
  <u>
    <h2 class="subtitle is-2">Summer Uniform:</h2>
  </u>
  <p>
    <li>Tartan summer weight skirt (length to be just below the knee)</li>
    <li>Blue culottes (optional)</li>
    <li>RR white short-sleeved shirt</li>
    <li>Navy cardigan or v-necked jersey</li>
    <li>Navy blazer</li>
    <li>
      White socks, short, with or without RR gold logo (optional with sandals
      but compulsory with lace-up shoes)
    </li>
    <li>Brown leather t-bar or u-bar sandals or Brown leather lace-up shoes</li>
    <li>RR navy or yellow waterproof jacket (optional)</li>

    <u>
      <h2 class="subtitle is-2">Winter Uniform:</h2>
    </u>
    <li>
      Kilt (length – midway between ankle and knee) or skirt (length to be just
      below the knee)
    </li>
    <li>Blue culottes (optional)</li>
    <li>RR white long-sleeved shirt</li>
    <li>Navy/gold striped tie (Year 11-12</li>
    <li>Gold tie (Year 13)</li>
    <li>Navy cardigan or v-necked jersey</li>
    <li>Navy blazer (blue and gold braid for Year 13)</li>
    <li>Navy tights or navy over the knee socks</li>
    <li>Brown leather t-bar or u-bar sandals or brown leather lace-up shoes</li>
    <li>RR navy or yellow waterproof jacket (optional)</li>

  </p>
</div>

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

<figure id="yr13winter">
  <img
    src="/images/yr13winter.png"
    alt="yr13winter"
    title="Image courtesy to Rangi Ruru" />
</figure>
</div>