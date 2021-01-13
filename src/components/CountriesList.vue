<template lang="html">
  <div>
      <select v-on:change="handleSelect($event)">
          <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
      </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js'
import ListItem from './ListItem.vue';

export default {
    name: "countries-list",
    props: ['countries', 'selected'],
    methods: {
        handleSelect: function(event) {
            this.selected = event.target.value;
            console.log('selected', this.selected);
            eventBus.$emit('selected', this.selected);
        }
    },
    components: {
        "list-item": ListItem
    }
}
</script>

<style lang="css" scoped>

</style>