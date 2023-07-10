<script setup>
</script>

<script>
import axios from "axios";

export default {
  name: 'SearchBox',
  methods: {
    async getData(query) {
      try {
        //fetch
        const response = await axios.get(this.$hostname + "songs?search=" + query + "&page=1");
        this.songs = response.data;
        this.$emit('newSongs', this.songs)
      }
      catch (error) {
        console.log(error);
      }
    },
  },
}
</script>

<template>
  <div class="flex w-4/5 h-12 rounded-lg shadow-lg bg-white overflow-hidden">
    <div class="grid place-items-center h-full w-12 text-gray-300">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
      </svg>
    </div>

    <input @input="getData($event.target.value)"
        class="peer h-full w-full outline-none text-sm text-gray-700 pr-2"
        type="text"
        id="search"
        placeholder="Search something..."
    />
  </div>
</template>

<style scoped>

</style>