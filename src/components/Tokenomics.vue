<template>
	<div class="tokenomics-wrapper">
		<h2>Tokenomics</h2>
		<div class="tokenomics-inner">
			<card class="tokenomics-left">
				<img src="@/assets/img/waschbaer2.png" alt="" />
			</card>
			<div class="tokenomics-right">
				<card class="tokenomics-card">
					<h3>TOTAL SUPPLY</h3>
					<p>todo</p>
				</card>
				<card class="tokenomics-card">
					<h3>TOKEN ADDRESS</h3>
					<p>todo</p>
				</card>
			</div>
		</div>
	</div>
</template>

<script setup>
import Card from "@/components/atomaric/Card.vue";
</script>

<style lang="sass">
.tokenomics-wrapper
    .tokenomics-inner
        display: flex
        gap: 20px
        .tokenomics-left
            img
                width: 300px
        .tokenomics-right
            display: flex
            flex-direction: column
            gap: 20px
            .tokenomics-card
                display: flex
                flex-direction: column
                align-items: center
                flex: 1 1 auto
                justify-content: center

                h3
                    margin-bottom: 10px
                p
                    color: #000
                    margin: 0
                    font-family: Gluten
                    font-size: 30px
                    font-style: normal
                    font-weight: 500
                    text-transform: capitalize
</style>
