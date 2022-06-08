<template>
  <div>
      <select name="" id="" v-model="select.value">
          <option value="">all</option>
          <option :value="genere" v-for="(genere, index) in select.listGenere" :key="index">{{genere}}</option>
      </select>
  </div>
</template>

<script>
import select from '../../shared/select';

export default {
    name: "SelectGenere",
    data() {
        return {
            select,
        }
    },
}
</script>

<style lang="scss" scoped>

</style>