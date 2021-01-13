<template lang="html">
  <div>
      <li v-on:click="handleClick">{{country.name}}</li>
  </div>
</template>

<script>
export default {
    name: 'list-item',
    props: ['country'],
    methods: {
        handleClick: function () {
            console.log('country', this.country)
        }
    }
}
</script>

<style>

</style>