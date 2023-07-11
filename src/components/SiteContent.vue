<script setup>
import RecordsRack from "@/components/RecordsRack.vue";
import SearchBox from "@/components/SearchBox.vue";
</script>

<script>
  // import axios from "axios";

  export default {
    methods: {
      async updateSongs(newSongs) {
        this.songData = []
        this.songs = newSongs
        /*let count = 0
        for(const s of this.songs) {
          console.log(s)
          let image = await axios.get(this.$hostname + 'img?id=' + s.pk)
          this.songData.push([this.songs[count], image])
          count++;
        }*/
      }
    },
    data() {
      return {
        songs: [],
        songData: [],
      }
    }
  }
</script>

<template>
  <div class="w-full justify-center flex-row flex pt-6 -mb-2">
    <SearchBox @newSongs="updateSongs"/>
  </div>
  <RecordsRack :displayed-songs="this.songs"/>
</template>

<style scoped>

</style>