<script setup>
import {ref, inject} from "vue"
import BuyButton from "@/components/atomaric/BuyButton.vue"
import IconHamburger from "./icons/IconHamburger.vue";
import IconClose from "./icons/IconClose.vue";

const menuOpen = inject('menuOpen')

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
	<div class="background"  @click="menuOpen =false" :class="{'menu-open': menuOpen}">
    </div>
        <header>
		<div class="navbar">
			<div class="navbar-left">
				<div class="navbar-icon">
					<img alt="Logo Token" class="logo" src="@/assets/img/logo.png" />
				</div>
				<div class="navbar-title">PEDRO</div>
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
                    <buy-button class="main-menu-link"></buy-button>
                    <icon-hamburger class="hamburger-button" @click="menuOpen = true"></icon-hamburger>
				</div>
			</div>
		</div>
	</header>
    <transition name="mobile-nav">
        <div class="mobile-menu" v-show="menuOpen">
            <div class="mobile-menu-inner">
                <icon-close class="close-button" @click="menuOpen = false"></icon-close>
               <div class="mobile-menu-links">
                <div
						class="mobile-menu-link"
						v-for="link in links"
						:key="link.name"
						@click="$emit('link-clicked', link.name);menuOpen=false"
					>
						{{ link.title }}
					</div>
                    
                </div>
                <buy-button></buy-button>
            </div>
        </div>
    </transition>
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
                font-size: 32px
                @media (min-width: 768px)
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
            .main-menu-links
                display: flex
                gap: 48px
                align-items: center
                &:hover, &:active, &:focus
                    color: lighten(black, 20%)
                .main-menu-link
                    display: none
                    cursor: pointer
                    @media (min-width: 768px)
                        display: block

.hamburger-button
    color: black
    height: 30px
    @media (min-width: 768px)
        display: none

.mobile-menu
    touch-action: none
    position: fixed
    height: 100vh
    top: 0
    right: 0
    padding: 15px 20px
    background-color: white
    width: 70%
    z-index: 100
    transform: translateX(0)
    &.mobile-nav-enter-active,
    &.mobile-nav-leave-active
        transition: .15s ease all
    &.moblie-nav-enter-from,
    &.mobile-nav-leave-to
        transform: translateX(100%)
    &.mobile-nav-enter-from
        transform: translateX(100%)
    .mobile-menu-inner
        text-align: right
        .mobile-menu-links
            text-align: center
            .mobile-menu-link
                padding: 12px
                font-size: 20px
                align-self: center
                &:hover, &:focus, &:active
                    background-color: darken(white, 10%)
        .token-button--buy
            margin-top: 15px
            text-align: center

        .close-button
            height: 30px
            align-self: end



.background
    &.menu-open
        touch-action: none
        background: black
        height: 100vh
        width: 100%
        z-index: 5
        position: fixed
        opacity: 0.5
        overflow: hidden
        
</style>
