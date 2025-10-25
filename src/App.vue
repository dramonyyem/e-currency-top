<script setup lang="ts">
import { RouterView } from 'vue-router'

</script>

<template>
  <header class="bg-black w-full h-[470px]">
    <div class="bg-white w-7/10 mx-auto h-full bg-cover " style="background-image: url('https://s.yimg.com/ny/api/res/1.2/q3wOWtuRyToXU0jSFNu6Aw--/YXBwaWQ9aGlnaGxhbmRlcjt3PTEyNDI7aD02OTk7Y2Y9d2VicA--/https://s.yimg.com/os/creatr-uploaded-images/2024-01/18116200-bb0f-11ee-abe4-1602dcadb608')">

    </div>
  </header>
  <main class="min-h-screen bg-white my-8">
    <RouterView />
  </main>
  <footer class="bg-purple-600 h-[200px]">

  </footer>

</template>

<style scoped>

</style>
