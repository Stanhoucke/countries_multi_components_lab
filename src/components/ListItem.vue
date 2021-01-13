<template lang="html">
    <option v-on:click="handleClick">{{country.name}}</option>
</template>

<script>
import { eventBus } from '../main.js';

export default {
    name: 'list-item',
    props: ['country'],
    methods: {
        handleClick: function () {
            // console.log('country', this.country)
            eventBus.$emit('country-selected', this.country);
        }
    }
}
</script>

<style>

</style>