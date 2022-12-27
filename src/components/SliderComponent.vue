<template>
  <div class="slider">
    <img v-bind:src="selectedImage" />
    <button v-on:click="prevSlide">prev</button>
    <button v-on:click="nextSlide">next</button>
  </div>
</template>

<script lang="ts">
export default {
  data() {
    return {
      index: 0,
      imageList: [
        "@/assets/img/horse-race.jpg",
        "@/assets/img/horse-dressure.jpg",
        "@/assets/img/horse-jump.jpg",
        "@/assets/img/horse-cowboy.jpg",
      ],
      selectedImage: "@/assets/img/horse-race.jpg",
    };
  },
  methods: {
    prevSlide() {
      this.index--;
      console.log(this.index);
      this.setSelectedImage();
    },
    nextSlide() {
      this.index++;
      console.log(this.index);
      this.setSelectedImage();
    },
    setSelectedImage() {
      this.selectedImage = this.imageList[this.index];
      console.log(this.selectedImage);
    },
  },
};
</script>
