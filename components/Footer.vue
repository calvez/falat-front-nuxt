<template>
    <footer class="p-4 shadow md:px-6 md:py-">
        <div class="sm:flex sm:items-center sm:justify-between">
            <a href="https://flowbite.com/" class="flex items-center mb-4 sm:mb-0 w-28">
                <Logo></Logo>
            </a>
            <ul class="flex flex-wrap items-center mb-6 text-sm text-gray-500 sm:mb-0 dark:text-gray-400">
                <li>
                    <a href="#" class="mr-4 hover:underline md:mr-6 ">Termékek</a>
                </li>
            </ul>
        </div>
    </footer>
</template>
<script>
import Logo from '@/components/Logo.vue'
export default {
    name: 'Footer',
}
</script>