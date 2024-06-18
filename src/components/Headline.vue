<template>
	<div class="token-headline">
		<div class="token-headline_left">
			<h1>PEDRO THE RACCOON</h1>
			<div class="social-wrapper">
				<social-item size="small" title="Telegram" :href="telegram" icon="telegram"></social-item>
				<social-item size="small" title="x/Twitter" :href="twitter" icon="x"></social-item>
				<social-item size="small" :href="discord" title="Discord" icon="discord"></social-item>
				<social-item size="small" title="Dexscreener" :href="descreener" icon="dex"></social-item>
				<social-item size="small" title="Uniswap" :href="uniswap" icon="uniswap"></social-item>
			</div>
		</div>
		<div class="token-headline_right">
			<img src="@/assets/img/giphy.webp" alt="" />
		</div>
	</div>
</template>

<script setup>
import SocialItem from "./atomaric/SocialItem.vue";

const telegram = import.meta.env.VITE_TELEGRAM;
const twitter = import.meta.env.VITE_TWITTER;
const discord = import.meta.env.VITE_DISCORD;
const uniswap = import.meta.env.VITE_UNISWAP;
const descreener = import.meta.env.VITE_DESCREENER;
</script>

<style lang="sass">
.token-headline
    background-color: black
    display: flex
    flex-direction: column
    color: white
    @media (min-width: 768px)
        flex-direction: row
    .token-headline_left, .token-headline_right
        flex: 1 1 auto
        display: flex
        flex-direction: column
        justify-content: center
        gap: 48px
        align-items: center
        .social-wrapper
            display: flex
            gap: 12px
    .token-headline_left
        flex: 1 1 40%
        h1
            text-align: center
    .token-headline_right
        img
            height: 400px
            width: 400px
</style>
