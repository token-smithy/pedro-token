<template>
	<div class="token-about">
		<h2>About</h2>
		<card>
			<div class="token-about_header">
				<p>
					One of the most memeable memecoin in 2024. <br />
					Time to join the raccoon dance.
				</p>
			</div>
			<div class="token-about_body">
				<iframe
					width="100%"
					height="400px"
					src="https://www.youtube.com/embed/Pb-HDNUSqrE?si=C9nO5P5fVLFvwnAb"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
					referrerpolicy="strict-origin-when-cross-origin"
					allowfullscreen
				></iframe>
			</div>
		</card>
	</div>
</template>

<script setup>
import Card from "./atomaric/Card.vue";
</script>

<style lang="sass">
.token-about
    .token-card
        padding: 28px 28px
        display: flex
        flex-direction: column
        gap: 24px
        .token-about_header
            text-align: center
            p
                margin: 0
                font-size: 24px
</style>
