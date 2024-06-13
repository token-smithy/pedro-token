<script setup>
import { ref, getCurrentInstance, provide } from "vue";
import VueHeader from "./components/Header.vue";
import VueFooter from "./components/Footer.vue";
import Tokenomics from "./components/Tokenomics.vue";
import Headline from "./components/Headline.vue";
import About from "./components/About.vue";
import { Vue3Marquee } from "vue3-marquee";

const home = ref();
const about = ref();
const tokenomics = ref();
const instance = getCurrentInstance();
const menuOpen = ref(false)
provide('menuOpen', menuOpen)

const words = [
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
	"$PEDRO",
];

function menuItemClicked(payLoad) {
	instance.refs[payLoad].scrollIntoView({ behavior: "smooth" });
}
</script>

<template>
	<div ref="home"></div>
	<vue-header @link-clicked="menuItemClicked"></vue-header>
	<main :class="{'menuOpen': menuOpen}" >
		<section id="home">
			<headline></headline>
			<Vue3Marquee>
				<span v-for="(word, index) in words" :key="index">
					{{ word }}
				</span>
			</Vue3Marquee>
		</section>
		<div class="container">
			<section id="about" ref="about">
				<about></about>
			</section>
			<section id="tokenomics" ref="tokenomics">
				<tokenomics></tokenomics>
			</section>
		</div>
		<vue-footer>^</vue-footer>
	</main>
</template>

<style lang="sass">
.token-headline
    height: calc(100vh - 66px - 38.5px)
.vue3-marquee
    background-color: black
    color: #f5bd03
    padding: 12px 0
    overflow: hidden
    .marquee
        justify-content: space-around
        gap: 12px
        @media (min-width: 768px)
            gap: 0

main
    &.menuOpen
        touch-action: none

    .container
        gap: 48px
        display: flex
        flex-direction: column
</style>
