<script setup lang="ts">
const route = useRoute()

const { data: docs } = await useAsyncData('documents-list', () => {

    return queryCollection('content').all()
})

</script>


<template>
    <main>
        <NuxtLink v-for="doc in docs" :key="doc.path" :to="doc.path">
            <h2>{{ doc.title }}</h2>
            <p>{{ doc.description }}</p>
        </NuxtLink>

    </main>
</template>