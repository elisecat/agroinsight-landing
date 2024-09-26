<template>
    <div class="container mx-auto py-6 max-w-4xl">
        <h1 class="text-4xl font-bold text-center w-full md:flex-grow">{{ sectionTitle }}</h1>
        <slot></slot>
    </div>
</template>

<script lang="ts" setup>
import { useRouter } from 'vue-router'

const props = defineProps({
    sectionTitle: {
        type: String,
        required: true
    },
    showBackButton: {
        type: Boolean,
        default: false
    }
})

const router = useRouter()

const goBack = () => {
    router.back()
}
</script>

<style scoped></style>
