<template>
  <header>
      <div class="logo">
          <img src="../../assets/img/spotify-logo.png" alt="logo-spotify">
      </div>
  </header>
</template>

<script>
export default {
    name: "baseHeader",
}
</script>

<style lang="scss" scoped>
header {
    background-color: #2e3a46;
    padding: 1.25rem;

    img {
        height: 3.125rem;
    }
}
</style>