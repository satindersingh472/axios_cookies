<template>
  <div id="app">
    <display-selection></display-selection>
    <dog-button></dog-button>
    <cat-button></cat-button>
  </div>
</template>

<script>
import DisplaySelection from "@/components/displaySelection.vue";
import DogButton from "@/components/dogButton.vue";
import CatButton from '@/components/catButton.vue';
export default {
  name: 'App',
  components: {
    DisplaySelection,
    DogButton,
    CatButton
  }
}
</script>

<style scoped>
#app{
  text-align: center;
  display: grid;
  gap: 20px;
}
</style>
