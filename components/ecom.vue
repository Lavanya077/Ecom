<template>
  <div class="whole">
    <div class="nav">
      <div class="logo">
        <img src="../assets/logoremove.png" alt="Logo" />
      </div>

      <div class="menu-icon sm:hidden" @click="show">
        <MdiIcon icon="mdiMenu" class="size-8" />
      </div>

      <div v-if="menuVisible" class="mobilemenu md:hidden">
        <a href="#" class="navitemmob">Home</a>
        <a href="#" class="navitemmob">About Us</a>
        <a href="#" class="navitemmob">Blogs</a>
        <a href="#" class="navitemmob">Shop</a>
        <a href="#" class="navitemmob">Contact Us</a>
      </div>

      <div class="navlinks">
        <a href="#" class="navitems">Home</a>
        <a href="#" class="navitems">About Us</a>
        <a href="#" class="navitems">Blogs</a>
        <a href="#" class="navitems">Shop</a>
        <a href="#" class="navitems">Contact Us</a>
      </div>

      <div class="navicons m-6">
        <MdiIcon icon="mdiAccountOutline" class="icons" />
        <MdiIcon icon="mdiMagnify" class="icons" />
        <MdiIcon icon="mdiCartOutline" class="icons" />
      </div>
    </div>

   
    <div class="caro">
      <div ref="container" class="caro-container">
        <div class="caroitem">
          <img src="../assets/image12.jpg" class="wall" />
          <h1 class="absolute left-1/2 transform -translate-x-1/2 top-60 text-4xl font-semibold font-sans">Sofa grace</h1>
        </div>
        <div class="caroitem">
          <img src="../assets/image7.jpg" class="wall" />
        </div>
        <div class="caroitem">
          <img src="../assets/image11.jpg" class="wall" />
        </div>
      </div>
      <MdiIcon icon="mdiChevronLeft" @click="prev" class="absolute top-1/2  left-4 size-12 stroke-white" />
      <MdiIcon icon="mdiChevronRight" @click="next" class="absolute top-1/2 right-4 size-12 stroke-white" />
    </div>
  </div>

  <div class="cat">
    <h1 class=" font-semibold font-2xl lg:font-bold lg:text-4xl items-center w-full flex justify-center lg:mt-8">Featured Categories</h1>
    <div class="con">
      <label>we just keep things minimal</label>
      <a href="#">view more</a>
    </div>
  </div>


</template>

<script setup>
import { ref } from 'vue'

const index = ref(0)
const container = ref(null)
const menuVisible = ref(false)

const updateCarousel = () => {
  if (container.value) {
    container.value.style.transform = `translateX(${-index.value * 100}%)`
  }
}

const next = () => {
  const slides = container.value?.children.length
  index.value = (index.value + 1) % slides
  updateCarousel()
}

const prev = () => {
  const slides = container.value?.children.length
  index.value = (index.value - 1 + slides) % slides
  updateCarousel()
}

const show = () => {
  menuVisible.value = !menuVisible.value
}
</script>

<style>
.navitems {
  @apply font-sans p-4 md:p-8 text-sm md:text-base font-medium my-4 md:my-6;
}
.navlinks {
  @apply hidden md:flex md:items-center w-full justify-center;
}
.logo {
  @apply w-16 h-16 p-2 md:w-24 md:h-24 lg:w-32 lg:h-32 md:mx-8 lg:mx-16;
}
.navicons {
  @apply hidden xl:flex xl:flex-row xl:items-center xl:absolute xl:top-4 xl:right-8;
}
.icons {
  @apply hidden lg:flex lg:w-8 lg:h-8 lg:m-4 ;
}

.nav {
  @apply flex items-center justify-between w-full p-4 md:p-0;
}
.caro {
  @apply relative w-full mx-auto overflow-hidden z-10;
}
.caro-container {
  @apply flex transition-transform ease-in-out duration-300 rounded-lg;
}
.caroitem {
  @apply min-w-full min-h-screen px-8 md:px-16 lg:px-24 rounded-2xl relative;
}
.menu-icon {
  @apply block md:hidden ml-auto mr-4;
}
.mobilemenu {
  @apply absolute top-16 left-0 w-full bg-white shadow-md flex flex-col items-center p-4 z-50;
}
.navitemmob {
  @apply font-sans text-base font-medium py-2;
}
.wall {
  @apply object-cover w-full h-full;
}
</style>
