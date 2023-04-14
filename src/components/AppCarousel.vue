<script>
export default {
  name: 'AppCarousel',
  data() {
    return {
      images: [
        require('@/components/media/banca1.png'),
        require('@/components/media/banca2.png'),
        require('@/components/media/banca3-1.png')
      ],
      activeIndex: 0
    }
  },
  methods: {
    slidePrev() {
      this.activeIndex = (this.activeIndex - 1 + this.images.length) % this.images.length;
    },
    slideNext() {
      this.activeIndex = (this.activeIndex + 1) % this.images.length;
    }
  },
};
</script>

<template>
  <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
    <div class="carousel-inner">
      <div v-for="(img, index) in images" :key="index" class="carousel-item" :class="{ active: activeIndex === index }">
        <img :src="img" class="d-block w-100" alt=""  width="100" height="350">
      </div>
    </div>
    <button @click="slidePrev" class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button @click="slideNext" class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>



<style></style>