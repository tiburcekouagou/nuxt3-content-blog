<script setup lang="ts">
import type { QueryBuilderParams } from '@nuxt/content/types';

const query: QueryBuilderParams = {
    path: "/posts",
    draft: false,
    sort: [
        {
            date: -1
        }
    ]
}

function formatDate(date: string) {
    return useDateFormat(date, "DD-MM-YYYY")
}

</script>
<template>
    <div>
        <ContentList path="/posts"  fields="title,date,thumbnail" :query="query">
            <template #default="{ list }">
                <div v-for="post in list" :key="post._path" class="blog-card bg-white rounded-2xl overflow-hidden mb-4">
                    <div class="h-[320px]">
                        <img :src="post.thumbnail" alt="" class="w-full h-full object-cover" />
                    </div>

                    <div class="blog-card-meta p-4">
                        <h3 class="text-2xl font-semibold">
                            <NuxtLink :to="post.slug">{{ post.title }}</NuxtLink>
                        </h3>
                        <div class="text-sm text-gray-500 mt-px">
                            {{ formatDate(post.date) }}
                        </div>
                    </div>
                </div>
            </template>
            <template #not-found>
                <p>No articles found.</p>
            </template>
        </ContentList>
    </div>
</template>