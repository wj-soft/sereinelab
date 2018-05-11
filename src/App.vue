<template>
  <div id="app">
    <selectItem></selectItem>
  </div>   
</template>

<script>
import selectItem from './components/selectItem.vue';

export default {
  data(){
    return {
      data: []
    }
  },
  components: {
    'selectItem': selectItem
  },
  methods: {
    
  }
}
</script>

<style>
</style>