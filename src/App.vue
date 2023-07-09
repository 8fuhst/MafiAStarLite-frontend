<template>
  <DefaultNavbar/>
  <RecordsRack/>
</template>

<script>
import RecordsRack from "@/components/RecordsRack.vue";
import DefaultNavbar from "@/components/DefaultNavbar.vue";

export default {
  name: 'App',
  components: {
    RecordsRack,
    DefaultNavbar,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
