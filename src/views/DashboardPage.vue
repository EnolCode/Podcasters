<script setup>
import { onBeforeMount, ref } from "vue";
import PodcastsService from "../services/PodcastService";
import CardPodcast from "../components/CardPodcast.vue";
import HeadPage from "../components/HeadPage.vue";
import FilterBar from "../components/FilterBar.vue";

const podcastService = new PodcastsService();
const podcasts = ref([]);

onBeforeMount(async () => {
  await podcastService.fetchAllPodcasts();
  podcasts.value = podcastService.getPodcasts();
});
</script>

<template>
  <main>
    <HeadPage />
    <FilterBar />
    <section>
      <CardPodcast v-for="podcast in podcasts" :podcast="podcast" />
    </section>
  </main>
</template>

<style scoped>
main{
  display: flex;
  flex-direction: column;;
}
section {
  margin: 0 auto;
  width: 80%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1em;
  justify-content: center;
  align-items: center;
}
</style>
