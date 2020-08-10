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
  h2 {
    margin-left: 210px;
  }

  div {
    margin-left: 110px;
  }

  #sportsuni {
    height: 400px;
    width: 300px;
  }


  /* ######## LAYOUT #########*/
  #grid-container {
    display: grid;
    grid:
      " text sportsuni " auto
      / auto auto;
  }

  #text {
    grid-area: text;
  }
  #sportsuni{
    grid-area: sportsuni;
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
      <h2 class="subtitle is-2">Sports Uniform:</h2>
    </u>
    <li>Rangi Ruru sports top</li>
    <li>Rangi Ruru navy sports shorts and Rangi Ruru trackpants (optional)</li>
    <li>Navy long-sleeved polypropylene top (optional)</li>
    <li>Rangi Ruru long sleeved rugby jersey or RRGS hoodie</li>
    <li>Sports shoes</li>
    <li>Sports socks</li>
    <li>Clan swimming cap</li>
    <li>
      Students playing in inter-school sports competitions must be dressed in
      correct
    </li>
    <li>
      sports uniform at all times. For travel to and from sports games the
      correct sports
    </li>
    <li>uniform must be worn.</li>
    <li>Sunhat optional for all year levels</li>
  </p>
</div>

<figure id="sportsuni">
  <img
    src="/images/sportsuni.png"
    alt="sportsuni"
    title="Image courtesy to Rangi Ruru" />
</figure>
</div>