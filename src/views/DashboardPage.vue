<script setup>
import { onBeforeMount, ref } from "vue";
import PodcastsService from "../services/PodcastService";
import CardPodcast from "../components/CardPodcast.vue";

const podcastService = new PodcastsService();
const podcasts = ref([]);
const authors = ref([]);

onBeforeMount(async () => {
  await podcastService.fetchAllPodcasts();
  await podcastService.fetchAllAuthors();
 podcasts.value = podcastService.getPodcasts();
 authors.value = podcastService.getAuthors();
  console.log(podcasts.value);
  console.log(authors.value);
});
</script>

<template>
  <CardPodcast v-for="podcast in podcasts" :podcast="podcast" />
  <!-- <h1 v-for="podcast in podcasts">{{ podcast }}</h1> -->
</template>

<style scoped></style>
