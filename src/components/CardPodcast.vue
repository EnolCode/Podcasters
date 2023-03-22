<script setup>
	import { defineProps } from "vue";

	const props = defineProps({
		podcast: Object,
	});
</script>

<template>
	<div class="card">
		<li>
			<img class="card__img" :src="podcast['im:image'][0].label" />
			<p class="card__title">{{ podcast["im:name"].label }}</p> 
			<p class="card__author">Author: {{ podcast["im:artist"].label }}</p> 
		</li>
	</div>
</template>

<style lang="scss">
	.card {
    margin: 0 auto;
    margin-bottom: 3em;
		width: 12em;
		height: 7em;
		background-color: red;
		color: black;
    text-align: center;
    // display: flex;
    // flex-direction: column;
    // justify-content: space-between;
    &__title {
      position: relative;
      bottom: 50px;
      font-size: .8em;
    }

    &__author {
      position: relative;
      bottom: 50px;
      font-size: .8em;
    }

    &__img {
      border-radius: 50%;
      width: 50%;
      height: 70%;
      position: relative;
      bottom: 55px;
      left: 50px;
    }

	}
</style>
