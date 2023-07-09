<script setup>
</script>

<script>
  export default {
    name: "SongBox",
    props: ['song']
  }
</script>

<template>
  <div class="flex w-1/3 flex-wrap px-3 mt-1 -mb-12">
    <div class="w-full px-2">
      <div class="relative overflow-hidden bg-cover bg-no-repeat" style="background-position: 50%">
        <img class="block w-full h-full rounded-lg object-cover object-center" src="..\assets\bliss.jpg"/>
        <div class="absolute rounded-lg bottom-0 right-0 left-0 top-0 h-full w-full bg-black bg-fixed opacity-50 overflow-hidden"></div>
      </div>
      <div class="relative inset-y-[-20%] bottom-5 hidden py-5 text-center text-white md:block">
        <p class="text-xl">{{ song.fields.song_name }}</p>
        <p class="text-base">{{ song.fields.song_artist}}</p>
      </div>
      <!--p class="py-2"> {{ song.fields.song_name }} - {{ song.fields.song_artist }} </p-->
    </div>
  </div>

  <!--div--
      data-te-carousel-init
      data-te-carousel-slide>
    <div
        class="relative w-full overflow-hidden after:clear-both after:block after:content-['']">
      <div
          class="relative float-left -mr-[100%] hidden w-full transition-transform duration-[600ms] ease-in-out motion-reduce:transition-none"
          data-te-carousel-active
          data-te-carousel-item
          style="backface-visibility: hidden">
        <div
            class="relative overflow-hidden bg-cover bg-no-repeat"
            style="background-position: 50%">
          <img
              src="https://tecdn.b-cdn.net/img/Photos/Slides/img%20(123).jpg"
              class="block w-full" />
          <div
              class="absolute bottom-0 left-0 right-0 top-0 h-full w-full overflow-hidden bg-black bg-fixed opacity-50"></div>
        </div>
        <div
            class="absolute inset-x-[15%] bottom-5 hidden py-5 text-center text-white md:block">
          <h5 class="text-xl">First slide label</h5>
          <p>
            Some representative placeholder content for the first slide.
          </p>
        </div>
      </div>
    </div>
  </div-->

</template>

<style scoped>

</style>