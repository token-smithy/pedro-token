<script setup>
import { ref, inject } from "vue";

const links = [
	{
		title: "Home",
		name: "home",
	},
	{
		title: "About",
		name: "about",
	},
	{
		title: "Tokenomics",
		name: "tokenomics",
	},
];
</script>

<template>
	<header>
		<div class="navbar">
			<div class="navbar-left">
				<div class="navbar-icon">
					<img alt="Logo Token" class="logo" src="@/assets/img/logo.png" />
				</div>
				<div class="navbar-title">$PEDRO</div>
			</div>
			<div class="navbar-inner">
				<div class="main-menu-links">
					<div
						class="main-menu-link"
						v-for="link in links"
						:key="link.name"
						@click="$emit('link-clicked', link.name)"
					>
						{{ link.title }}
					</div>
				</div>
			</div>
		</div>
	</header>
</template>

<style lang="sass" scoped>
header
    .navbar
        position: fixed
        z-index: 3
        box-sizing: border-box
        background-color: white
        width: 100%
        border-bottom: 2px solid black
        display: flex
        justify-content: space-between
        .navbar-left
            display: flex
            align-items: center
            gap: 24px
            .navbar-title
                font-size: 48px
            .navbar-icon
                img
                    height: 60px
                    // @media (min-width: 1200px)
                    //     height: 80px
                    //     width: 160px
        .navbar-inner
            display: flex
            align-items: center
            padding: 0 20px
            // @media (min-width: 1200px)
            //     padding: 40px 80px
            .main-menu-links
                margin-right: 48px
                display: flex
                gap: 48px
                &:hover, &:active, &:focus
                    color: lighten(black, 20%)
                .main-menu-link
                    cursor: pointer
</style>
