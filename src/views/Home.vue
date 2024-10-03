<template>
    <div class="container mx-auto flex justify-center">
        <img src="../assets/app-img.png" alt="agroinsight-slogan" class="w-full max-w-4xl h-auto" />
    </div>
    <PageLayout sectionTitle="Descarga tu app AgroInsight">
        <div class="container mx-auto max-w-4xl bg-white shadow-lg rounded-lg p-6 text-center">
            <p class="text-lg mb-4">
                La solución ideal para proteger sus cultivos de maíz contra el gusano cogollero. Nuestra app detecta
                esta plaga de manera temprana y precisa, ofreciéndole recomendaciones y reportes personalizados para
                asegurar la salud y productividad de sus cultivos.
            </p>
            <div class="flex justify-center space-x-4 mt-6">
                <BaseButton variant="green" size="lg">
                    <a href="/AgroInsight.apk" download>Descarga la app ahora</a>
                </BaseButton>
            </div>
        </div>
    </PageLayout>
</template>

<script lang="ts">
import { useRouter } from 'vue-router'
import PageLayout from '@/components/shared/PageLayout.vue'
import BaseButton from '@/components/shared/BaseButton.vue'

export default {
    components: { PageLayout, BaseButton },
    setup() {
        const router = useRouter()

        const navigateToHeroes = () => {
            router.push('/heroes')
        }

        const navigateToCreate = () => {
            router.push('/heroes/create')
        }

        return { navigateToHeroes, navigateToCreate }
    }
}
</script>