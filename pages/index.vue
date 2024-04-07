<template>
  <div>
    <Navigation />
    <HeroSection />
    <HospitalsList />
    <!-- <ul>
      <li v-for="hospital in hospitals" :key="hospital.h_id">
        {{ hospital.h_name }}
      </li>
    </ul> -->
  </div>
</template>

<script setup>
// import axios from "axios";

// async function getData() {
//   try {
//     const response = await axios.get(
//       "http://localhost/statista-api/endpoint.php/hospitals"
//     );
//     return response.data;
//   } catch (error) {
//     console.error("Error fetching data:", error);
//     throw error;
//   }
// }

// let hospitals = ref([]);

// onMounted(async () => {
//   hospitals.value = await getData();
// });
</script>
