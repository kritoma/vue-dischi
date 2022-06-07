<template>
  <div class="albums">
      <img :src="album.poster" :alt="album.title">
      <h3>{{album.title}}</h3>
      <div class="author">{{album.author}}</div>
      <div class="year">{{album.year}}</div>
  </div>
</template>

<script>
export default {
    name: "cardAlbum",
    props: {
        album: Object,
    }
}
</script>

<style lang="scss" scoped>
.albums {
    background-color: #2e3a46;
    padding: 20px;
    text-align: center;
    color: white;
    height: 100%;
    
    img {
        width: 100%;
    }

    h3 {
        text-transform: uppercase; 
        margin: .9375rem 0;
    }

    .author, .year {
        color: #6a6867;
    }
}
</style>