<template lang="html">
  <!-- <p>country</p> -->
  <div class="">
    <li v-on:click="handleClick">{{ country.name }}</li>
  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country'],
  methods: {
    handleClick() {

    }
  }
}
</script>

<style lang="css" scoped>
</style>
