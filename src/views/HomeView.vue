<script setup>
import { RouterLink } from 'vue-router';


</script>

<template>
  <main class="flex-1 ml-64 p-8">
            <!-- Hero Section -->
            <section class="bg-white rounded-lg shadow-md overflow-hidden mb-8">
                <div class="relative">
                    <img src="https://picsum.photos/1200/400?random=20" alt="Hero image" class="w-full h-96 object-cover">
                    <div class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center text-center px-4">
                        <div class="text-white">
                            <h1 class="text-4xl md:text-5xl font-bold mb-4">Welcome to My Blog</h1>
                            <p class="text-xl md:text-2xl mb-8">Exploring ideas, sharing knowledge, and connecting with readers</p>
                            <a href="#featured" class="bg-blue-500 text-white px-6 py-3 rounded-lg hover:bg-blue-600 transition duration-200 inline-block">Explore Posts</a>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Featured Posts Section -->
            <section id="featured" class="mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Featured Posts</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Featured Post 1 -->
                    <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                        <img src="https://picsum.photos/800/400?random=21" alt="Blog post" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <div class="flex items-center mb-3">
                                <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">Technology</span>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">The Future of Web Development</h3>
                            <p class="text-gray-600 mb-4">Exploring upcoming trends and technologies shaping the web development landscape...</p>
                            <RouterLink :to="{name: 'post',params : {id: 22}}"  class="text-blue-500 hover:text-blue-600 font-medium">Read More →</RouterLink>
                        </div>
                    </article>

                    <!-- Featured Post 2 -->
                    <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                        <img src="https://picsum.photos/800/400?random=22" alt="Blog post" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <div class="flex items-center mb-3">
                                <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">Design</span>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">UI/UX Design Principles</h3>
                            <p class="text-gray-600 mb-4">Essential principles for creating user-friendly and aesthetically pleasing interfaces...</p>
                            <RouterLink :to="{name: 'post',params : {id: 21}}"  class="text-blue-500 hover:text-blue-600 font-medium">Read More →</RouterLink>
                        </div>
                    </article>

                    <!-- Featured Post 3 -->
                    <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                        <img src="https://picsum.photos/800/400?random=23" alt="Blog post" class="w-full h-48 object-cover">
                        <div class="p-6">
                            <div class="flex items-center mb-3">
                                <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">Programming</span>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">Modern JavaScript Features</h3>
                            <p class="text-gray-600 mb-4">Deep dive into the latest JavaScript features and best practices for modern web development...</p>
                            <!-- <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a> -->
                            <RouterLink :to="{name: 'post',params : {id: 20}}"  class="text-blue-500 hover:text-blue-600 font-medium">Read More →</RouterLink>
                        </div>
                    </article>
                </div>
            </section>
        </main>
</template>
