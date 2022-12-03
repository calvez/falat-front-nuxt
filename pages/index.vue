<template>
    <div class="overflow-x-auto relative">
      <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
          <tr>
            <th scope="col" class="py-3 px-6">
              Termék neve
            </th>
            <th scope="col" class="py-3 px-6">
              Leírás
            </th>
            <th scope="col" class="py-3 px-6">
              Ár
            </th>
            <th scope="col" class="py-3 px-6">
              Műveletek
            </th>
          </tr>
        </thead>
        <tbody v-for="product in products" :key="product.id">
          <tr class="bg-white border-b dark:bg-gray-800 dark:border-gray-700">
            <th scope="row" class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap dark:text-white">
              {{ product.name }}
            </th>
            <td class="py-4 px-6">
              {{ product.description }}
            </td>
            <td class="py-4 px-6">
              {{ product.price }}
            </td>
            <td class="py-4 px-6">
              CRUD
            </td>
          </tr>
        </tbody>
      </table>
    </div>
</template>
<script>
export default {
  name: 'IndexPage',
  async asyncData({ $axios, $config }) {
    const products = await $axios.$get(`/products`)
    return { products }
  }
}
</script>