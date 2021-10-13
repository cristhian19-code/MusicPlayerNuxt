<template>
  <section class="container-music d-flex" style="height:100vh;">
    <div class="options-buttons col-2 col-md-1">
      <Navbar />
    </div>
    <div class="section-music col-10 col-md-11 px-3 pb-5">
      <Nuxt />
      <div class="play-music d-flex justify-content-start fixed-bottom">
        <b-navbar class="p-3 text-white justify-content-around align-items-center" style="width:100%;background:#0B0B0B" type="light">
            <div>
              <p class="h4">Shape of You</p>
              <p class="h6">Edd sheeran</p>
            </div>
            <div class="d-flex justify-content-center">
              <b-button class="btn-play rounded-circle mx-2">
                  <b-icon icon="skip-start"></b-icon>
              </b-button>
              <b-button class="btn-play rounded-circle mx-2">
                  <b-icon icon="play"></b-icon>
              </b-button>
              <b-button class="btn-play rounded-circle mx-2">
                  <b-icon icon="skip-end"></b-icon>
            </b-button>
          </div>
        </b-navbar>
      </div>
    </div>
  </section>
</template>
<script>
import NavbarVue from '../components/Navbar.vue'
export default {
  component:{
    NavbarVue
  }  
}
</script>
<style>
  .options-buttons{
    height: 100%;
  }

  .container-music,
  .options-buttons{
    background: #07151C ;
  }
  
  .section-music{
    border-radius: 20px 0 0 20px;
    height: 100%;
    width: 100%;
    overflow-y: scroll;
    position: static;
    background: #0B0B0B ;
  }

  .container-music{
    height: 100%;
  }
</style>