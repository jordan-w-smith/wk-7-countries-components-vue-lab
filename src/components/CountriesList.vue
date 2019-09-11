<template lang="html">
  <div class="">
    <select v-on:change="handleChange" v-model="selectedCountry" >
      <list-component v-for="(country, index) in countries" :key="index" :country="country"></list-component>
    </select>

  </div>
</template>

<script>
import ListComponent from './ListComponent.vue'
import { eventBus } from '../main.js'
export default {
  name: 'countries-list',
  props: ['countries'],
  data: function(){
    return {selectedCountry: ""}
  },
  methods: {
    handleChange () {
    eventBus.$emit('country-selected', this.selectedCountry)
    }
  },
  components: {
    "list-component": ListComponent
  }

}
</script>

<style lang="css" scoped>
</style>
