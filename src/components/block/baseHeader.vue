<template>
  <header>
      <div class="logo">
          <img src="../../assets/img/spotify-logo.png" alt="logo-spotify">
      </div>
      <div>
          <SelectGenere/>
      </div>
  </header>
</template>

<script>
import SelectGenere from '../common/SelectGenere.vue';

export default {
  components: { SelectGenere },
    name: "baseHeader",

}
</script>

<style lang="scss" scoped>
header {
    background-color: #2e3a46;
    padding: 1.25rem;
    display: flex;
    justify-content: space-between;
    align-items: center;

    img {
        height: 3.125rem;
    }
}
</style>