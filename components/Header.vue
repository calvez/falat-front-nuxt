<template>
    <div>
        <div class="relative bg-white">
            <div class="max-w-7xl px-4 sm:px-6">
                <div
                    class="flex border-b-2 border-gray-100 py-6 md:justify-start md:space-x-10">
                    <div class="flex justify-start lg:w-0 lg:flex-1">
                        <Logo></Logo>
                    </div>
                    <div class="-my-2 -mr-2 md:hidden">
                        <button type="button"
                            class="inline-flex items-center justify-center rounded-md bg-white p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
                            aria-expanded="false">
                            <span class="sr-only">Open menu</span>
                            <!-- Heroicon name: outline/bars-3 -->
                            <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                <path stroke-linecap="round" stroke-linejoin="round"
                                    d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" />
                            </svg>
                        </button>
                    </div>
                    <div class="hidden items-center justify-end md:flex md:flex-1 lg:w-0">
                        <a href="#"
                            class="whitespace-nowrap text-base font-medium text-gray-500 hover:text-gray-900">Belépés</a>
                        <a href="#"
                            class="ml-8 inline-flex items-center justify-center whitespace-nowrap rounded-md border border-transparent bg-indigo-600 px-4 py-2 text-base font-medium text-white shadow-sm hover:bg-indigo-700">Regisztráció</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import Logo from '@/components/Logo.vue'
export default {
    name: 'Header',
}
</script>