<template>
  <div class="pb-4">
    <div class="d-flex justify-content-between">
      <div class="d-flex py-3">
        <b-button class="mx-1 rounded-circle">
          <b-icon icon="chevron-compact-left"></b-icon>
        </b-button>
        <b-button class="mx-1 rounded-circle">
          <b-icon icon="chevron-compact-right"></b-icon>
        </b-button>
      </div>
      <div class="d-flex align-items-center">
        <b-button class="mx-2  rounded-circle">
          <b-icon icon="lock"></b-icon>
        </b-button>
        <b-avatar variant="info" src="https://placekitten.com/300/300"></b-avatar>
      </div>
    </div>
    <p style="font-size:30px" class="mt-2 font-weight-bold text-white">Made for you</p>
    <div class="cards-musics d-flex flex-wrap justify-content-center pb-4" v-if="items">
      <MusicVue v-for="(item, index) in items" :key="index" :data="{
        title: item.title_short,
        title_album: item.album.title,
        name: item.artist.name,
        cover_big: item.album.cover_big
      }"/>
    </div>
   
  </div>
</template>

<script>
import MusicVue from '../components/Music.vue'

export default {
  components:{
    MusicVue
  },
  data() {
    return {
      Client_ID: '3c6d54fcd08f428b9a9d3462e99b3acc',
      Client_Secret: 'bb54087e5b6e40bda3365e8d94733b50',
    }
  },
  async asyncData() {
    var items = []
    await fetch("https://deezerdevs-deezer.p.rapidapi.com/search?q=ed sheeran", {
      "method": "GET",
      "headers": {
        "x-rapidapi-key": "c750f476e6mshf8d1c90e5b2142bp17510cjsn09f1faa45bb3",
        "x-rapidapi-host": "deezerdevs-deezer.p.rapidapi.com"
      }
    })
    .then(async response => {
      const data = await response.json();
      items = data.data
    })
    .catch(err => {
      console.error(err);
    });
    
    return {
      items
    }
  },
}
</script>
<style>
  .cards-music{
    overflow-x: scroll;
    overflow-y: hidden;
    grid-gap: 10px;
  }
  .cards-musics{
    grid-gap: 15px;
  }

  .rounded-circle{
    background: #1B1919;
    height: 50px;
    width: 50px;
  }

</style>