<template>
  <div>
    <!-- Overlay Animasi -->
    <div
      v-if="visible"
      class="fixed inset-0 bg-light bg-opacity-85 flex items-center justify-center z-50"
    >
      <div class="text-dark text-3xl font-bold animate-fade-out">
        byntangxyz links
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const visible = ref(true);

onMounted(() => {
  // Mengatur visible menjadi false setelah 3 detik (durasi overlay)
  setTimeout(() => {
    visible.value = false;
  }, 3000); // Durasi animasi
});
</script>

<style>
@keyframes fadeOut {
  0% {
    opacity: 1;
    transform: scale(1);
  }
  50% {
    opacity: 0.5;
    transform: scale(1.1);
  }
  100% {
    opacity: 0;
    transform: scale(1.2);
  }
}

.animate-fade-out {
  animation: fadeOut 1.5s ease-in-out forwards; /* Durasi animasi diperpanjang menjadi 1.5 detik */
}
</style>
