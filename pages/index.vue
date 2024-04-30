<script setup lang="ts"></script>
<template>
    <div>
        <ContentList path="/posts">
            <template #default="{ list }">
                {{ list }}
            </template>
            <template #not-found>
                <p>No articles found.</p>
            </template>
        </ContentList>
    </div>
</template>