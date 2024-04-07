<template>
  <div class="container mx-auto px-4 mb-10">
    <div>
      <h2 class="text-primary text-2xl pb-1">Who are</h2>
      <h2 class="text-3xl mb-5">World's Best Hospitals 2023</h2>
    </div>
    <div class="filters mb-4">
      <form class="flex space-x-4 items-center">
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
          id="search"
          name="search"
          class="w-full border-gray-300 rounded-lg shadow-sm focus:border-primary focus:ring-primary"
          placeholder="Enter your search term..."
        />
        <button
          type="submit"
          class="w-1/2 px-4 py-2 rounded-lg shadow-md text-white bg-primary hover:bg-black focus:outline-none focus:ring-black"
        >
          Search
        </button>
      </form>
    </div>

    <!-- ============ Table  =========== -->
    <div class="mt-10 flex flex-col">
      <div class="-mt-2 -mx-4 sm:-mx-6 lg:-mx-8 overflow-x-auto">
        <div class="inline-block min-w-full py-2 align-middle md:px-6 lg:px-8">
          <div
            class="overflow-hidden shadow ring-1 ring-black ring-opacity-5 md:rounded-lg"
          >
            <table class="min-w-full divide-y divide-grey-300">
              <thead class="bg-grey-50">
                <th scope="col" class="table-header">Column Name</th>
                <th scope="col" class="table-header">Column Name</th>
                <th scope="col" class="table-header">Column Name</th>
                <th scope="col" class="table-header">Column Name</th>
              </thead>
              <tbody>
                <tr>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                </tr>

                <tr>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                </tr>

                <tr>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                  <td class="table-data">Lorem Ipsum</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped></style>
