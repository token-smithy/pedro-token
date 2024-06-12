<template>
	<div class="token-headline">
		<div class="token-headline_left">
			<h1>PEDRO THE RACCOON</h1>
			<div class="social-wrapper">
				<social-item size="small" title="Telegram" icon="telegram"></social-item>
				<social-item size="small" title="x/Twitter" icon="x"></social-item>
				<social-item size="small" title="Discord" icon="discord"></social-item>
				<social-item size="small" title="Dexscreener" icon="dex"></social-item>
				<social-item size="small" title="Uniswap" icon="uniswap"></social-item>
			</div>
		</div>
		<div class="token-headline_right">
			<img src="@/assets/img/pedro-racoon.gif" alt="" />
		</div>
	</div>
</template>

<script setup>
import SocialItem from "./atomaric/SocialItem.vue";
</script>

<style lang="sass">
.token-headline
    background-color: black
    display: flex
    color: white
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
