<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

</script>

<template>
  <!-- Nav Container -->
  <nav>
    <!-- Flex Container for all items -->
    <div class="mx-auto pt-3 px-5 md:px-10 lg:px-20 bg-gray-50">
      <!-- Flex Container for Logo/Menu -->
      <div class="flex items-center gap-15">
        <!-- Logo -->
        <img src="../assets/logo.svg" alt="logo" class="h-6 md:h-7 lg:h-8 mt-2">
        <!-- Left Menu -->
        <div class="hidden lg:flex gap-8">
          <a href="">Features</a>
          <a href="">Pricing</a>
          <a href="">Resources</a>
        </div>
        <!-- Right Button Mn -->
        <div class="ml-auto ">
          <div class="hidden lg:flex items-center text-center gap-5">
            <a href="">Login</a>
            <a href="" class="bg-cyan-500 text-white rounded-full py-2 w-22">Sign up</a>
          </div>
          <svg @click="toggleMenu" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="size-6 md:size-7 lg:hidden block ">
            <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
          </svg>
        </div>

      </div>
      <!-- MOBILE MENU -->
      <transition name="fade">
        <div v-show="isMenuOpen"
          class="lg:hidden mt-6 bg-white shadow-lg rounded-xl p-6 flex flex-col gap-4 text-center font-semibold">
          <a href="#" @click="isMenuOpen = false">Features</a>
          <a href="#" @click="isMenuOpen = false">Pricing</a>
          <a href="#" @click="isMenuOpen = false">Resources</a>

          <hr class="my-3">

          <a href="#" @click="isMenuOpen = false">Login</a>
          <a href="#" @click="isMenuOpen = false" class="bg-cyan-500 text-white py-2 rounded-full">
            Sign up
          </a>
        </div>
      </transition>


    </div>
  </nav>
</template>

<style scoped></style>