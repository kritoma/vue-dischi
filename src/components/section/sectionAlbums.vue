<template>
  <section>
      <div class="container">
          <div class="list_album">
              <div class="album" v-for="(album, index) in filterSong" :key="index">
                  <cardAlbum :album="album"/>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import cardAlbum from '../common/cardAlbum.vue';
import axios from 'axios';
import select from '../../shared/select';

export default {
  components: { cardAlbum },
    name: "sectionAlbums",
    data() {
        return {
            albums: [],
            select,
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.albums = response.data.response;
            
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        })
    },
    computed: {
        filterGenere() {
            let albumsGenere = [];
            this.albums.forEach((elm) => {
                if(!albumsGenere.includes(elm.genre)) {
                    albumsGenere.push(elm.genre);
                }
            });
            select.listGenere = albumsGenere;
            return albumsGenere;
        },

        filterSong() {
            if(this.select.value === "") {
                return this.albums
            }

            return this.albums.filter((elm) => 
                elm.genre === this.select.value
            )
            }
    },

    

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