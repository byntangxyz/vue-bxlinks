<script setup>
import Main from "./main.vue";
</script>

<template>
  <div
    class="relative min-h-screen bg-light flex items-center justify-center overflow-hidden"
  >
    <!-- Lingkaran Biru Muda -->
    <div
      class="absolute w-72 h-72 bg-blue-300 rounded-full blur-xl mix-blend-multiply animate-move1"
      style="top: 10%; left: 20%"
    ></div>

    <!-- Lingkaran Merah Muda -->
    <div
      class="absolute w-80 h-80 bg-pink-300 rounded-full blur-xl mix-blend-multiply animate-move2"
      style="top: 30%; left: 60%"
    ></div>

    <!-- Lingkaran Ungu Muda -->
    <div
      class="absolute w-64 h-64 bg-purple-300 rounded-full blur-xl mix-blend-multiply animate-move3"
      style="top: -70%; left: 20%"
    ></div>

    <!-- Lingkaran Hijau Muda -->
    <div
      class="absolute w-96 h-96 bg-green-300 rounded-full blur-xl mix-blend-multiply animate-move4"
      style="top: 60%; left: 5%"
    ></div>

    <!-- Lingkaran Kuning Muda -->
    <div
      class="absolute w-72 h-72 bg-yellow-300 rounded-full blur-xl mix-blend-multiply animate-move5"
      style="top: 20%; left: 80%"
    ></div>
    <div class="relative lg:w-3/4 lg:h-3/4 mx-4 my-4">
      <div
        class="bg-white bg-opacity-70 rounded-lg shadow-2xl flex text-center justify-center items-center"
      >
        <Main />
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes move1 {
  0%,
  100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  50% {
    transform: translateY(-100px) translateX(150px) scale(1.1);
  }
}

@keyframes move2 {
  0%,
  100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  50% {
    transform: translateY(120px) translateX(-100px) scale(0.9);
  }
}

@keyframes move3 {
  0%,
  100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  50% {
    transform: translateY(250px) translateX(-150px) scale(1.2);
  }
}

@keyframes move4 {
  0%,
  100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  50% {
    transform: translateY(180px) translateX(200px) scale(0.8);
  }
}

@keyframes move5 {
  0%,
  100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  50% {
    transform: translateY(-200px) translateX(-50px) scale(1.3);
  }
}

.animate-move1 {
  animation: move1 8s ease-in-out infinite;
}

.animate-move2 {
  animation: move2 10s ease-in-out infinite;
}

.animate-move3 {
  animation: move3 12s ease-in-out infinite;
}

.animate-move4 {
  animation: move4 14s ease-in-out infinite;
}

.animate-move5 {
  animation: move5 16s ease-in-out infinite;
}
</style>
