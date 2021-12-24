<template>
  <div class="gallery-wrapper flex flex-col">
    <ul class="h-full grid grid-cols-3 sm:grid-cols-4 xl:grid-cols-6 the-grid">
      <li v-for="(i, index) in images" :key="i.index" @click="loadPopup(index)">
        <img
          :src="i.src"
          :alt="`Amir Sakira photo 0${index}`"
          class="w-full h-full object-cover"
        />
      </li>
    </ul>
    <transition name="fade">
      <div v-if="showPopup" class="popup" @click="showPopup = false">
        <div
          class="flex w-full h-screen justify-center items-center bg-dark-800 bg-opacity-80"
        >
          <img :src="imageSrc" alt="" class="shadow rounded-xl" />
        </div>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showPopup: false,
      selectedImage: 1,
    }
  },
  computed: {
    images() {
      const arr = []
      for (let index = 0; index < 12; index++) {
        arr.push({ index, src: `/photos/as_${index + 1}.jpg` })
      }
      return arr
    },
    imageSrc() {
      return `/photos/as_${this.selectedImage + 1}.jpg`
    },
  },
  methods: {
    loadPopup(index) {
      this.selectedImage = index
      this.showPopup = true
    },
  },
}
</script>
<style scoped>
h2 {
  display: none;
  color: #ad974f;
  font-size: 2.3rem;
  line-height: 2.3rem;
  padding: 2rem 0 1rem 0;
  text-align: center;
  font-weight: 700;
}
.popup {
  height: 100vh;
  width: 100vw;
  position: absolute;
  top: 0;
}
.gallery-wrapper {
  height: 100%;
}
.the-grid {
  grid-auto-rows: 22% 22% 22% 34%;
}
img {
}
@media only screen and (min-width: 640px) {
  .the-grid {
    grid-auto-rows: 33% 33% 34%;
  }
}
@media only screen and (min-width: 1280px) {
  .the-grid {
    grid-auto-rows: 50% 50%;
  }
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-active {
  opacity: 0;
}
</style>
