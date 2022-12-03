<template>
    <div>
        <div class="h-screen bg-white flex flex-col  items-center">
            <div class="bg-white w-96 shadow-xl rounded p-5">
                <h1 class="text-3xl font-medium">Termék szerkesztése: {{ product.name }}</h1>
                <form v-on:submit.prevent="submitForm" class="space-y-5 mt-5">
                    <label for="name" class="form-label inline-block mt-2 text-gray-700">Termék neve</label>
                    <input type="text" name="name" class="w-full h-12 border border-gray-800 rounded px-3"
                        :placeholder="product.name" :value="product.name" />
                    <label for="description" class="form-label inline-block mt-2 text-gray-700">Termék leírása</label>
                    <textarea rows="5" cols="33" type="text" name="description"
                        class="w-full h-12 border border-gray-800 rounded px-3" :placeholder="product.description"
                        :value="product.description" />
                    <label for="price" class="form-label inline-block mt-2 text-gray-700">Termék ára</label>
                    <input type="number" name="price" class="w-full h-12 border border-gray-800 rounded px-3"
                        :placeholder="product.price" :value="product.price" />
                    <div class="">
                        <a href="#!" class="font-medium text-blue-900 hover:bg-blue-300 rounded-md p-2">
                            <NuxtLink to="/">Vissza</NuxtLink>
                        </a>
                    </div>
                    <button class="text-center w-full bg-blue-900 rounded-md text-white py-3 font-medium">
                        <NuxtLink to="/">Mentés</NuxtLink>
                    </button>
                </form>
            </div>
        </div>

    </div>
</template>
<script>
export default {
    data() {
        return {
            product: {
                name: '',
                description: '',
                price: '',
            }
        }
    },
    async asyncData({ $axios, $config, params }) {
        const product = await $axios.$get(`products/${params.id}`)
        return { product }    
    }
}
</script>
