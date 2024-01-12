<template>
    <MusicLayout>
        <template #title>
            Musiques
        </template>


        <template #action>
            <Link :href="route('tracks.create')"
            class="text-white bg-gradient-to-r from-blue-500 via-blue-600 to-blue-700 hover:bg-gradient-to-br focus:ring-4 focus:outline-none focus:ring-blue-300 dark:focus:ring-blue-800 shadow-lg shadow-blue-500/50 dark:shadow-lg dark:shadow-blue-800/80 font-medium rounded-lg text-sm px-5 py-2.5 text-center me-2 mb-2"

            >
                Créer une musique
            </Link>
        </template>


        <template #content>
            <h1>Track</h1>
            <div v-for="music in tracks" :key="music.uuid" :class="[music.id % 2 ? 'text-red-500' : 'text-green-500']">
                {{ music.id }} : {{ music.title }}
            </div>
        </template>
    </MusicLayout>
</template>

<script>
import MusicLayout from '@/Layouts/MusicLayout.vue';
import { Link } from '@inertiajs/vue3';

export default {
    components:{
        MusicLayout,
        Link,
    },
    props: {
        tracks: Array
    }
}
</script>

<style>

</style>