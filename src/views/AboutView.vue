<script setup>
 import {team} from '../data/team.js'
 console.log(team);
</script>

<template>
    <main class="flex-1 ml-64 p-8">
            <!-- About Section -->
            <section class="bg-white rounded-lg shadow-md overflow-hidden mb-8">
                <div class="p-8">
                    <h1 class="text-3xl font-bold text-gray-800 mb-6">About Us</h1>
                    <p class="text-gray-600 mb-6">Welcome to My Blog, a platform dedicated to sharing knowledge and insights about web development, design, and technology. Our mission is to create a community where developers and designers can learn, grow, and connect with like-minded individuals.</p>
                    <p class="text-gray-600 mb-6">Founded in 2024, we've been committed to providing high-quality content that helps our readers stay up-to-date with the latest trends and best practices in the industry.</p>
                </div>
            </section>

            <!-- Team Section -->
            <section class="mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Our Team</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <!-- Team Member 1 -->
                    <div v-for="(parson,index ) in team" class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img :src="`https://picsum.photos/400/400?random=${index}`" alt="Team member" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">{{ parson.name }}</h3>
                            <p class="text-gray-600 mb-4">{{ parson.title }}</p>
                            <p class="text-gray-600">{{ parson.about }}</p>
                        </div>
                    </div>

                    <!-- Team Member 2 -->
                    <!-- <div class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img src="https://picsum.photos/400/400?random=2" alt="Team member" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">Jane Smith</h3>
                            <p class="text-gray-600 mb-4">Senior UI/UX Designer</p>
                            <p class="text-gray-600">Expert in creating beautiful and user-friendly interfaces that delight users.</p>
                        </div>
                    </div> -->

                    <!-- Team Member 3 -->
                    <!-- <div class="bg-white rounded-lg shadow-md overflow-hidden">
                        <img src="https://picsum.photos/400/400?random=3" alt="Team member" class="w-full h-64 object-cover">
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-gray-800 mb-2">Mike Johnson</h3>
                            <p class="text-gray-600 mb-4">Content Strategist</p>
                            <p class="text-gray-600">Crafting engaging content and building meaningful connections with our readers.</p>
                        </div>
                    </div> -->
                    
                </div>
            </section>
        </main>
</template>