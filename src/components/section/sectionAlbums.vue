<template>
  <section>
      <div class="container">
          <div class="list_album">
              <div class="album" v-for="(album, index) in albums" :key="index">
                  <cardAlbum :album="album"/>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import cardAlbum from '../common/cardAlbum.vue';
import axios from 'axios';

export default {
  components: { cardAlbum },
    name: "sectionAlbums",
    data() {
        return {
            albums: [],
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.albums = response.data.response;
            console.log(this.albums)
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
    }
}
</script>

<style lang="scss" scoped>
section {
    background-color: #1e2d3b;
    min-height: calc(100vh - 90px);
    padding: 20px;

    .list_album {
        display: flex;
        flex-wrap: wrap;
        gap: 1.25rem;


        .album {
            width: calc(100% / 5 - 20px);
            
        }
    }


}
</style>