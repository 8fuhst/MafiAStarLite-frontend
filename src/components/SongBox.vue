<script setup>
</script>

<script>
  //import axios from "axios";

  export default {
    name: "SongBox",
    props: ['song'],
    /*methods: {
      async getImage() {
        this.image = await axios.get(this.$hostname + 'img?id=' + this.song.pk)
      }
    },
    created() {
      this.getImage()
    }*/
  }
</script>

<template>
  <div v-if="song" class="flex w-1/3 flex-wrap px-3 -mb-12">
    <div class="w-full px-2">
      <div class="relative overflow-hidden bg-cover bg-no-repeat" style="background-position: 50%">
        <img class="block w-full h-full rounded-lg object-cover object-center" src="../assets/bliss.jpg"/>
        <div class="absolute rounded-lg bottom-0 right-0 left-0 top-0 h-full w-full bg-black bg-fixed opacity-50 overflow-hidden"></div>
      </div>
      <div class="relative inset-y-[-20%] bottom-5 hidden py-5 text-center text-white md:block">
        <p class="text-xl">{{ song.fields.song_name }}</p>
        <p class="text-base">{{ song.fields.song_artist }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>