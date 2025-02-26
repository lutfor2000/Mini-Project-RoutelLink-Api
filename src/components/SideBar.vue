<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
     <aside class="w-64 bg-white shadow-md fixed h-full left-0 overflow-y-auto">
            <nav class="p-4">
                <ul class="space-y-2">
                    <li>
                        <RouterLink to="/" class="flex items-center space-x-2 p-2 hover:bg-blue-50 rounded-lg text-gray-700 hover:text-blue-600 transition duration-200">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>Home</span>
                        </RouterLink>
                    </li>
                    <li>
                        <RouterLink to="/about" class="flex items-center space-x-2 p-2 bg-blue-50 rounded-lg text-blue-600 transition duration-200">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                            </svg>
                            <span>About</span>
                        </RouterLink>
                    </li>
                    <li>
                        <RouterLink to="/contact" class="flex items-center space-x-2 p-2 hover:bg-blue-50 rounded-lg text-gray-700 hover:text-blue-600 transition duration-200">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                            </svg>
                            <span>Contact</span>
                        </RouterLink>
                    </li>
                    <li>
                        <RouterLink to="/blog" class="flex items-center space-x-2 p-2 hover:bg-blue-50 rounded-lg text-gray-700 hover:text-blue-600 transition duration-200">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 20H5a2 2 0 01-2-2V6a2 2 0 012-2h10a2 2 0 012 2v1m2 13a2 2 0 01-2-2V7m2 13a2 2 0 002-2V9.5a2 2 0 00-2-2h-2" />
                            </svg>
                            <span>Blog</span>
                        </RouterLink>
                    </li>
                </ul>
            </nav>
        </aside>
</template>