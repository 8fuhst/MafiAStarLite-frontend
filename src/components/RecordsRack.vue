<script setup>
</script>

<script>
import SongBox from "@/components/SongBox.vue";
import axios from "axios";

export default {
  name: "RecordsRack",
  components: {
    SongBox
  },
  data() {
    return {
      songs: ['']
    }
  },
  methods: {
    async getData() {
      try {
        //fetch
        const response = await axios.get('http://127.0.0.1:8000/api/songs?search=Muse');
        console.log(response.data);
        this.songs = response.data;
      }
      catch (error) {
          console.log(error);
      }
    },
  },
  created() {
    this.getData();
  }
}
</script>

<template>
  <div class="songs_container mx-auto px-5 py-2 lg:px-32 lg:pt-12">
    <div class="songs_content align-middle flex flex-wrap justify-evenly">
        <songBox v-for="song in songs" :key="song.song_id" :song=song></songBox>
    </div>
  </div>
</template>

<style scoped>

</style>