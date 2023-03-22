<script setup>
	import { onBeforeMount, ref } from "vue";
	import PodcastsService from "../services/PodcastService";
	import CardPodcast from "../components/CardPodcast.vue";
	import HeadPage from "../components/HeadPage.vue";

	const podcastService = new PodcastsService();
	const podcasts = ref([]);

	onBeforeMount(async () => {
		await podcastService.fetchAllPodcasts();
		podcasts.value = podcastService.getPodcasts();
	});
</script>

<template>
  <HeadPage />
	<main>
		<CardPodcast
			v-for="podcast in podcasts"
			:podcast="podcast"
		/>
	</main>
</template>

<style scoped>
main {
  margin: 0 auto;
  width: 80%;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1em;
  justify-content: center;
  align-items: center;
}
</style>
