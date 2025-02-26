<script setup>
import { ref,onBeforeMount } from 'vue';
import { RouterLink } from 'vue-router';

const posts = ref([]);

//----lode more-------------
const allPost = ref([]);
const offset = ref([0]);
const limit = 10;

onBeforeMount(async () =>{
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    const data = await response.json();
    allPost.value = data; //-----Load more -data stock
    posts.value = data.slice(0,10);
    // allPost.value = data;
    // console.log(posts.value)
})

const loadMore = () =>{
    offset.value += limit;
    const nextPosts = allPost.value.slice(offset.value, offset.value + limit) ;
    posts.value = [...posts.value, ...nextPosts];
}



</script>

<template>
    <main class="flex-1 ml-64 p-8">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Blog Post Cards -->
                <article v-for="post in posts" :key="post.id" class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img :src="`https://picsum.photos/800/400?random=${post.id}`" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img :src="`https://picsum.photos/32/32?random=${post.id}`" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-blue-100 text-blue-800 text-xs font-medium px-2.5 py-0.5 rounded">Programming</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">{{ post.title }}</h2>
                        <p class="text-gray-600 mb-4">{{post.body}}</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">5 min read</span>
                            <RouterLink :to="{name: 'post',params: {id: post.id}}"  class="text-blue-500 hover:text-blue-600 font-medium">Read More →</RouterLink>
                        </div>
                    </div>
                </article>

                <!-- <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img src="https://picsum.photos/800/400?random=3" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img src="https://picsum.photos/32/32?random=4" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-green-100 text-green-800 text-xs font-medium px-2.5 py-0.5 rounded">Technology</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">The Future of Web Development</h2>
                        <p class="text-gray-600 mb-4">Explore the latest trends and technologies shaping the future of web development in 2024 and beyond...</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">8 min read</span>
                            <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a>
                        </div>
                    </div>
                </article>

                <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img src="https://picsum.photos/800/400?random=5" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img src="https://picsum.photos/32/32?random=6" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-purple-100 text-purple-800 text-xs font-medium px-2.5 py-0.5 rounded">Design</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">UI/UX Design Principles</h2>
                        <p class="text-gray-600 mb-4">Discover essential design principles that will help you create more intuitive and user-friendly interfaces...</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">6 min read</span>
                            <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a>
                        </div>
                    </div>
                </article>

                <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img src="https://picsum.photos/800/400?random=7" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img src="https://picsum.photos/32/32?random=8" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-red-100 text-red-800 text-xs font-medium px-2.5 py-0.5 rounded">Security</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">Web Security Best Practices</h2>
                        <p class="text-gray-600 mb-4">Learn essential security practices to protect your web applications from common vulnerabilities and threats...</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">10 min read</span>
                            <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a>
                        </div>
                    </div>
                </article>

                <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img src="https://picsum.photos/800/400?random=9" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img src="https://picsum.photos/32/32?random=10" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-yellow-100 text-yellow-800 text-xs font-medium px-2.5 py-0.5 rounded">Mobile</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">Responsive Design Techniques</h2>
                        <p class="text-gray-600 mb-4">Master the art of creating responsive websites that work flawlessly across all devices and screen sizes...</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">7 min read</span>
                            <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a>
                        </div>
                    </div>
                </article>

                <article class="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition duration-200">
                    <img src="https://picsum.photos/800/400?random=11" alt="Blog post" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <div class="flex items-center mb-3">
                            <img src="https://picsum.photos/32/32?random=12" alt="Author" class="w-8 h-8 rounded-full mr-3">
                            <span class="bg-indigo-100 text-indigo-800 text-xs font-medium px-2.5 py-0.5 rounded">Performance</span>
                        </div>
                        <h2 class="text-xl font-semibold text-gray-800 mb-2">Web Performance Optimization</h2>
                        <p class="text-gray-600 mb-4">Discover techniques and tools to optimize your website's performance and improve user experience...</p>
                        <div class="flex items-center justify-between">
                            <span class="text-sm text-gray-500">9 min read</span>
                            <a href="single.html" class="text-blue-500 hover:text-blue-600 font-medium">Read More →</a>
                        </div>
                    </div>
                </article> -->

            </div>
            <div class="flex justify-center mt-8">
            <button @click="loadMore" class="bg-blue-500 text-white px-6 py-3 rounded-lg hover:bg-blue-600 transition duration-200">Load More</button>
        </div>
        </main>
</template>