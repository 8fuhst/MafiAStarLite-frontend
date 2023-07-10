<script setup>
import RecordsRack from "@/components/RecordsRack.vue";
import SearchBox from "@/components/SearchBox.vue";
</script>

<script>
  export default {
    methods: {
      async updateSongs(newSongs) {
        this.songs = newSongs
      }
    },
    data() {
      return {
        songs: ['']
      }
    }
  }
</script>

<template>
  <div class="w-full justify-center flex-row flex pt-6 -mb-2">
    <SearchBox @newSongs="updateSongs"/>
  </div>
  <RecordsRack :displayed-songs="songs"/>
</template>

<style scoped>

</style>