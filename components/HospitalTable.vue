<template>
  <div class="filters mb-4">
    <form
      class="flex space-x-4 items-center"
      @submit.prevent="fetchFilteredData"
    >
      <select
        id="country"
        name="country"
        class="w-1/2 border-gray-300 rounded-lg shadow-sm focus:border-primary focus:ring-primary"
      >
        <option value="">Select Country</option>
        <option value="us">United States</option>
        <option value="de">Germany</option>
        <option value="es">Spain</option>
        <option value="at">Austria</option>
      </select>
      <input
        type="text"
        v-model="searchTerm"
        id="search"
        name="search"
        class="w-full border-gray-300 rounded-lg shadow-sm focus:border-primary focus:ring-primary"
        placeholder="Enter the city"
      />
      <button
        type="submit"
        class="w-1/2 px-4 py-2 rounded-lg shadow-md text-white bg-primary hover:bg-black focus:outline-none focus:ring-black"
      >
        Search
      </button>
    </form>
  </div>

  <div class="mt-10 flex flex-col">
    <div class="overflow-x-auto">
      <div class="inline-block min-w-full py-2 align-middle">
        <div
          class="overflow-hidden shadow ring-1 ring-black ring-opacity-5 md:rounded-lg"
        >
          <table
            class="min-w-full divide-y divide-grey-300"
            v-if="hospitals.length > 0"
          >
            <thead class="bg-grey-50">
              <th scope="col" class="table-header">Hospital</th>
              <th scope="col" class="table-header">Country</th>
              <th scope="col" class="table-header">City</th>
              <th scope="col" class="table-header">Proms</th>
              <th scope="col" class="table-header">Rank</th>
            </thead>
            <tbody>
              <tr v-for="hospital in hospitals" :key="hospital.h_id">
                <td class="table-data">{{ hospital.h_name }}</td>
                <td class="table-data">{{ hospital.h_country }}</td>
                <td class="table-data">{{ hospital.h_city }}</td>
                <td class="table-data">{{ hospital.h_proms }}</td>
                <td class="table-data">{{ hospital.h_rank }}</td>
              </tr>
            </tbody>
          </table>
          <div v-else>No hospitals found.</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      hospitals: [],
      baseUrl: "http://localhost/statista-backend",
      searchTerm: "",
    };
  },
  methods: {
    async fetchData() {
      try {
        const resp = await axios.get(`${this.baseUrl}/get_data`);
        this.hospitals = resp.data;
      } catch (error) {
        console.error(error);
      }
    },
    async fetchFilteredData() {
      console.log(this.searchTerm);
      try {
        const resp = await axios.get(
          `${this.baseUrl}/get_filtered_data/${this.searchTerm}`
        );
        this.hospitals = resp.data;
      } catch (error) {
        console.error(error);
      }
    },
  },
  mounted() {
    this.fetchData();
  },
};
</script>

<style lang="scss" scoped></style>
