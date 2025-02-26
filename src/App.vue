<script setup>
import { RouterLink, RouterView } from 'vue-router'
import SideBar from './components/SideBar.vue';

</script>

<template>
  
  <header class="bg-white shadow-md fixed w-full top-0 z-50">
        <div class="container mx-auto px-4 py-4">
            <div class="flex items-center justify-between">
                <h1 class="text-2xl font-bold text-gray-800">My Blog</h1>
                <div class="flex items-center space-x-4">
                    <input type="search" placeholder="Search..." class="px-4 py-2 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500">
                    <button class="bg-blue-500 text-white px-4 py-2 rounded-lg hover:bg-blue-600 transition duration-200">Search</button>
                </div>
            </div>
        </div>
    </header>

    <!-- Sidebar and Main Content Container -->
    <div class="flex min-h-screen pt-20">
      <!-- Sidebar Navigation -->
       <side-bar/>
       <!-- Main Content -->
        <RouterView/>
        

    </div>

    <!-- Footer -->
    <footer class="bg-white shadow-md mt-8 ml-64">
        <div class="container mx-auto px-4 py-6">
            <div class="flex flex-col md:flex-row justify-between items-center">
                <div class="text-gray-600 mb-4 md:mb-0">
                    © 2024 My Blog. All rights reserved.
                </div>
                <div class="flex space-x-6">
                    <a href="#" class="text-gray-600 hover:text-blue-500 transition duration-200">Privacy Policy</a>
                    <a href="#" class="text-gray-600 hover:text-blue-500 transition duration-200">Terms of Service</a>
                    <a href="#" class="text-gray-600 hover:text-blue-500 transition duration-200">Contact Us</a>
                </div>
            </div>
        </div>
    </footer>

</template>

<style scoped>

</style>
