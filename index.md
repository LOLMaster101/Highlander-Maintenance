<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
  integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous" />
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
  integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
  integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js"
  integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
<link rel="stylesheet" href="styles.css">
<style>
  .active .slide-caption {
    text-align: center;
    display: block;
    margin-top: 5px;
  }

  .slide-caption {
    display: none;
    -webkit-transition-property: visibility;
    -webkit-transition-duration: 0.3s;
    -webkit-transition-timing-function : ease-in-out;
    transition-property: visibility;
    transition-duration: 0.3s;
    transition-timing-function : ease-in-out;
  }

  .expanded{
    width: 75%;
    text-align: center;
    padding-top: 1.5%;
    margin-left: auto;
    margin-right: auto;
  }

  p.expanded{
    margin-bottom: 0;
    overflow: scroll;
  }

</style>

<div class="modal fade" id="expanded-image" tabindex="-1" role="dialog" aria-labelledby="expandedImage" aria-hidden="true">
  <div class="modal-dialog modal-xl modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="image-expansion">Expanded Image</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div style="text-align: center" class="modal-body">
        <img class="expanded" src="" alt="">
        <p class="expanded"></p>
      </div>
    </div>
  </div>
</div>

<div id="slideshow" class="carousel slide" data-interval="false">
  <div class="carousel-inner">
     <div class="carousel-item active">
      <img
        class="d-block w-100"
        src="https://thehighlandernews.com/wp-content/uploads/2020/06/Drummer-in-circle-475x317.jpg"
      />
      <div class="slide-caption"><p>jfdkjfdksfjdskfjsdakfjsdakfjdsfkasdjfkdfjadkfjadsf;dsfjadsk
        4883983159843590834584239-5890483259897658493481984398123948132904823901489483948324902832901384130294812348
      </p></div>
    </div>
    <div class="carousel-item">
      <img
        class="d-block w-100"
        src="https://thehighlandernews.com/wp-content/uploads/2020/06/Emmett-Till-sign-475x317.jpg"
      />
        <div class="slide-caption"><p>abcdef</p></div>
    </div>
    <a
      class="carousel-control-prev"
      href="#slideshow"
      role="button"
      data-slide="prev"
      ><span class="carousel-control-prev-icon" aria-hidden="true"></span
      ><span class="sr-only">Previous</span></a>
      <a
      class="carousel-control-next"
      href="#slideshow"
      role="button"
      data-slide="next"
      ><span class="carousel-control-next-icon" aria-hidden="true"></span
      ><span class="sr-only">Next</span></a
    >
  </div>
</div>

<button id="expand-btn" class="btn btn-primary" style="font-family: europa, sans-serif;" data-target="#expanded-image" data-toggle="modal" type="button">
  View full image
</button>
<script>
  let link = "";
  let caption = "";

  let mObserver = new MutationObserver(function(mutations){
    mutations.forEach(function(mutation){
    console.log(mutation);
    link = jQuery(".active img").attr("src");
    caption = jQuery(".active p").html();
    const indexOfSize = link.search("-475x317");
    link = link.slice(0, indexOfSize) + ".jpg";
    jQuery("img.expanded").attr("src", link);
    jQuery("p.expanded").html(caption);
    });
      
  });
  mObserver.observe(jQuery("#expanded-image")[0], {attributes: true});

</script>
