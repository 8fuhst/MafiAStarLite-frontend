<script setup>
import RecordsRack from "./RecordsRack.vue";
import SearchBox from "./SearchBox.vue";
import UpdateButton from "./UpdateButton.vue";
</script>

<script>
  import axios from "axios";

  export default {
    methods: {
      async updateSongs(query) {
        this.page = 1;
        const response = await axios.get(this.$hostname + "songs?search=" + query + "&page=" + this.page);
        this.songs = response.data;
        this.query = query;
        this.buttonEnabled = response.data.length === 9;
      },
      async addSongs() {
        this.page++;
        const response = await axios.get(this.$hostname + "songs?search=" + this.query + "&page=" + this.page);
        this.songs = this.songs.concat(response.data)
        this.buttonEnabled = response.data.length === 9;
      }
    },
    data() {
      return {
        songs: undefined,
        query: undefined,
        page: 1,
        buttonEnabled: false
      }
    },
    created() {
      this.updateSongs("");
    }
  }
</script>

<template>
  <div class="w-full justify-center flex-row flex pt-6 -mb-2">
    <SearchBox @newSongs="updateSongs"/>
  </div>
  <RecordsRack :displayed-songs="songs"/>
  <div v-if="buttonEnabled" class="flex w-full justify-center">
    <UpdateButton @click="addSongs"/>
  </div>
</template>

<style scoped>

</style>
