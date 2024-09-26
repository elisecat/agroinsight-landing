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
                    <a href="https://drive.google.com/uc?export=download&id=16BkoWxdumBDJ4F_oFuoJBnIsdvXoB6qx"
                        download>Descarga la app ahora</a>
                </BaseButton>
            </div>
        </div>
    </PageLayout>
</template>

<script lang="ts">
import { useRouter } from 'vue-router'
import PageLayout from '@/components/shared/PageLayout.vue'
import BaseButton from '@/components/shared/BaseButton.vue'
import { useHeroesStore } from '@/stores/heroesStore'
import { computed, onMounted } from 'vue'

export default {
    components: { PageLayout, BaseButton },
    setup() {
        const router = useRouter()
        const heroesStore = useHeroesStore()

        const hasSuperheroes = computed(() => heroesStore.heroes.length > 0)

        onMounted(async () => {
            await heroesStore.fetchHeroes()
        })

        const navigateToHeroes = () => {
            router.push('/heroes')
        }

        const navigateToCreate = () => {
            router.push('/heroes/create')
        }

        const navigateToPentathlon = () => {
            if (heroesStore.heroes.length >= 3) {
                router.push('/pentathlon')
            } else {
                alert('You need at least 3 superheroes to participate in the pentathlon!')
            }
        }

        return { navigateToHeroes, navigateToCreate, navigateToPentathlon, hasSuperheroes, heroesStore }
    }
}
</script>