<script>
  import { stores } from "@sapper/app";
  const { session } = stores();
  session.garments = [];
</script>

<style>
  /*#####banner image####*/
  #banner {
    height: 250px;
    width: 2000px;
    margin-left: 15%;
  }
  /*#####map image####*/
  #map {
    height: 100px;
    width: 1000px;
    margin-left: 15%;
  }

  /*#####rangi button#####*/
  div {
    text-align: center;
  }
</style>

<!---the css styling the banner image, map image, and the rangi button.-->
<!---banner image-->
<figure id="banner">
  <img
    src="/images/banner.png"
    alt="banner"
    title="Image courtesy to Rangi Ruru" />
</figure>
<!---button taking you to the options page-->
<div>
  <a class="button is-large" href="options" style="margin:20px;">
    Rangi Ruru UNIFORM SHOP
  </a>
</div>
<!---main map image of rangiruru on front page-->
<p>
  <figure id="map">
    <img src="/images/map.png" alt="map" />
  </figure>
</p>
