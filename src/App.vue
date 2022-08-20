<template>
  <div id="app">
    <div>
    <dog-button></dog-button>
    <cat-button></cat-button>
    </div>
    <div>
    <display-selection></display-selection>
    </div>
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
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  justify-items: start;
}
</style>
