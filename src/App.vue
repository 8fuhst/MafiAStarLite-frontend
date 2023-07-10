<template>
  <DefaultNavbar/>
  <SiteContent/>
</template>

<script>
import DefaultNavbar from "@/components/DefaultNavbar.vue";
import SiteContent from "@/components/SiteContent.vue";

export default {
  name: 'App',
  components: {
    SiteContent,
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
