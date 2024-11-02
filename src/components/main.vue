<script setup>
import Card from "./Card.vue";
import { ref, onMounted } from "vue";

// Waktu sekarang dalam zona waktu Jakarta (GMT+7)
const currentTime = ref("");

const updateTime = () => {
  const formatter = new Intl.DateTimeFormat("en-US", {
    timeZone: "Asia/Jakarta",
    hour: "2-digit",
    minute: "2-digit",
    second: "2-digit",
    hour12: false,
  });
  currentTime.value = formatter.format(new Date());
};

// Perbarui waktu setiap detik
onMounted(() => {
  updateTime(); // Setel waktu saat komponen dipasang
  setInterval(updateTime, 1000); // Perbarui waktu setiap detik
});
</script>

<template>
  <main class="container mx-auto p-4">
    <div class="mb-8 flex items-center justify-between">
      <h1 class="text-dark text-xl font-bold">byntangxyz</h1>
      <img
        src="/logo.png"
        alt="logo byntangxyz"
        class="w-[50px] h-[50px] hover:animate-spin-slow"
      />
    </div>

    <div class="flex flex-wrap md:gap-8 lg:flex-nowrap">
      <div class="lg:w-1/2 space-y-4">
        <div class="grid grid-cols-2 gap-4">
          <div
            class="flex items-center justify-center bg-gradient-to-b from-blue-200 via-cyan-100 to-sky-200 shadow-md rounded-md h-32"
          >
            <div class="absolute">
              <p class="text-lg font-bold text-gray-700 block">
                {{ currentTime }}
              </p>
              <p class="mt-2 text-sm text-gray-500 block">GMT+7 Jakarta</p>
            </div>
          </div>
          <div
            class="flex items-center justify-center bg-white shadow-md rounded-md h-32"
          >
            <a
              href="https://byntangxyz.my.id"
              class="hover:scale-125 transition"
            >
              <i class="ph ph-globe text-black text-6xl"></i>
              <p class="font-semibold">Website</p>
            </a>
          </div>
        </div>

        <div
          class="bg-white shadow-md rounded-md flex flex-col items-center justify-center p-4"
        >
          <div
            class="map-container w-full h-64 lg:h-96 mx-auto hidden lg:block"
          >
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d247.04671626871917!2d110.37842102662309!3d-7.816534355245014!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e7a57a0070696a1%3A0xc85ce98b09574bb0!2sJl.%20Sorosutan%20No.1%2C%20Sorosutan%2C%20Kec.%20Umbulharjo%2C%20Kota%20Yogyakarta%2C%20Daerah%20Istimewa%20Yogyakarta%2055162!5e0!3m2!1sid!2sid!4v1730540952170!5m2!1sid!2sid"
              style="border: 0; width: 100%; height: 100%"
              allowfullscreen
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
          <h3 class="lg:hidden">This currently missing spot, <a href="https://github.com/vue-bxlinks" class="text-secondary">any ideas?</a></h3>
        </div>
      </div>

      <section id="links" class="lg:w-1/2 mt-4">
        <div class="grid grid-cols-1 gap-4">
          <Card v-for="(card, index) in cards" :key="index" :card="card" />
        </div>
        <div
          style="left: 0; width: 100%; height: 152px; position: relative"
          class="mt-8"
        >
          <iframe
            src="https://open.spotify.com/embed/track/4n7jnSxVLd8QioibtTDBDq?utm_source=generator&theme=0"
            style="
              top: 0;
              left: 0;
              width: 100%;
              height: 100%;
              position: absolute;
              border: 0;
            "
            allowfullscreen
            allow="clipboard-write; encrypted-media; fullscreen; picture-in-picture;"
          ></iframe>
        </div>
      </section>
    </div>
  </main>
</template>

<script>
import Card from "./Card.vue"; // Import komponen Card

export default {
  components: {
    Card, // Daftarkan komponen Card
  },
  data() {
    return {
      currentCard: 0, // Kolom default yang ditampilkan pada perangkat mobile
      cards: [
        // Objek untuk menyimpan informasi kartu
        {
          title: "Instagram",
          description: "See my daily updates!",
          link: "https://instagram.com/byntangxyz",
        },
        {
          title: " Github",
          description: "All of my projects are here",
          link: "https://github.com/byntangxyz",
        },
        {
          title: "Blog",
          description: "My article & blog about IT",
          link: "https://bxfundz.my.id",
        },
        {
          title: "Coming soon",
          description: "Untrafic links",
          link: "#",
        },
      ],
    };
  },
};
</script>

<style scoped>
.map-container {
  position: relative;
  width: 100%;
  padding-bottom: 75%; /* Rasio aspek lebih tinggi, bisa sesuaikan */
  height: 0;
  overflow: hidden;
  max-width: 1200px; /* Batas maksimum untuk layar besar */
  margin: auto; /* Agar peta berada di tengah */
}

.map-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border: 0;
}
</style>
