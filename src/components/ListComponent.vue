<template lang="html">
  <!-- <p>country</p> -->
  <!-- <div class=""> -->
    <option v-bind:value="country">{{ country.name }}</option>
  <!-- </div> -->
</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'list-component',
  props: ['country'],
  methods: {
    handleClick() {
      eventBus.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
