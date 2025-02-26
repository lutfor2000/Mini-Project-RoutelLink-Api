<script setup>
import { useRoute,useRouter } from 'vue-router'
import{ref, onBeforeMount} from 'vue'
// import router from '@/router';
const post = ref([]);
const route = useRoute();
const router = useRouter();
const postId = route.params.id;

onBeforeMount(async()=>{
    const response = await fetch(`https://jsonplaceholder.typicode.com/posts/${postId}`);
    const data = await response.json();
    post.value = data;
    console.log(post.value)
})


const goBack = ()=>{
    router.back();
}

</script>

<template>
    <main class="flex-1 ml-64 p-8">
            <article class="bg-white rounded-lg shadow-md overflow-hidden">
                <img src="https://picsum.photos/1200/400?random=13" alt="Blog post" class="w-full h-64 object-cover">
                <div class="p-8">
                    
                    <button @click="goBack" class="mb-4 text-gray-500 hover:text-blue-500">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 inline-block mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                    </svg>
                    Back
                    </button>

                    <div class="flex items-center mb-4">
                        <img src="https://avatar.iran.liara.run/public" alt="Author" class="w-10 h-10 rounded-full mr-4">
                        <div>
                            <h3 class="font-medium text-gray-800">John Doe</h3>
                            <span class="text-sm text-gray-500">Posted on January 15, 2024</span>
                        </div>
                    </div>
                    <h1 class="text-3xl font-bold text-gray-800 mb-4">{{ post.title }}</h1>
                    <div class="prose max-w-none">
                      <p>{{ post.body }}</p>
                    </div>
                    <div class="mt-8 pt-8 border-t border-gray-200">
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-4">
                                <button class="flex items-center space-x-2 text-gray-500 hover:text-blue-500">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
                                    </svg>
                                    <span>Like</span>
                                </button>
                                <button class="flex items-center space-x-2 text-gray-500 hover:text-blue-500">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z" />
                                    </svg>
                                    <span>Comment</span>
                                </button>
                            </div>
                            <div class="flex items-center space-x-4">
                                <button class="flex items-center space-x-2 text-gray-500 hover:text-blue-500">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8.684 13.342C8.886 12.938 9 12.482 9 12c0-.482-.114-.938-.316-1.342m0 2.684a3 3 0 110-2.684m0 2.684l6.632 3.316m-6.632-6l6.632-3.316m0 0a3 3 0 105.367-2.684 3 3 0 00-5.367 2.684zm0 9.316a3 3 0 105.368 2.684 3 3 0 00-5.368-2.684z" />
                                    </svg>
                                    <span>Share</span>
                                </button>
                                <button class="flex items-center space-x-2 text-gray-500 hover:text-blue-500">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 5a2 2 0 012-2h10a2 2 0 012 2v16l-7-3.5L5 21V5z" />
                                    </svg>
                                    <span>Save</span>
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </article>
        </main> 
</template>