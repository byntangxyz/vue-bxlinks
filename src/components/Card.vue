<template>
  <a :href="card.link" class="">
    <div
      class="bg-gradient-to-tl from-slate-200 via-cyan-100 to-slate-100 px-4 py-1 text-dark rounded-lg shadow-lg w-64 transition-transform transform hover:scale-105 min-w-16"
    >
      <h3 class="text-sm font-bold lg:text-lg">{{ card.title }}</h3>
      <p class="text-gray-800 text-xs lg:text-base">{{ card.description }}</p>
    </div>
  </a>
</template>

<script>
export default {
  props: {
    card: {
      type: Object,
      required: true,
    },
  },
};
</script>
