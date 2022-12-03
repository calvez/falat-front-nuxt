<template>
  <div class="overflow-x-auto relative">
    <table class="table-fixed text-sm text-left border-separate border-spacing-2 border border-slate-500">
      <thead class="text-xs text-gray-700 uppercase bg-gray-200">
        <tr>
          <th scope="col" class="py-3 px-6">
            ID
          </th>
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
      <tbody v-for="(product, index) in products.data" :key="product.id">
        <tr class="bg-white border-b">
          <td class="py-4 px-6">
            {{ product.id }}
          </td>
          <th scope="row" class="py-4 px-6 font-medium text-gray-900 whitespace-nowrap">
            <NuxtLink :to="`/${product.id}`">
              {{ product.name }}
            </NuxtLink>
          </th>
          <td class="py-4 px-6">
            {{ product.description }}
          </td>
          <td class="py-4 px-6 whitespace-nowrap">
            <span class="price">
              {{ product.price }} Ft
            </span>
          </td>
          <td class="py-4 px-6 border border-slate-700">
            <button @click="update(product.id)"><img class="w-6 fill-blue-700" src="../assets/img/edit.svg"
                alt="Szerkesztés" /></button>
            <button @click="del(product.id)"><img class="w-6 fill-blue-700" src="../assets/img/trash-solid.svg"
                alt="Törlés" /></button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios, $config }) {
    const products = await $axios.$get(`products`)
    return { products }
  },

  name: 'IndexPage',

  data() {
    return {
      showModal: false,
      products: []
    }
  },

  methods: {
    async update(id, color) {
      await window.axios.put(`/api/cruds/${id}`, { color });
      // Once AJAX resolves we can update the Crud with the new color
      this.products.find(crud => crud.id === id).color = color;
    },
    async create() {
      const { data } = window.axios.get('/api/cruds/create');
      this.products.push(new Crud(data));
    },
    async del(id) {
      await this.$axios.delete(`products/${id}`);
      let index = this.products.data.findIndex(products => id === id);
      this.products.data.splice(index, 1);
    }
  }
};
</script>