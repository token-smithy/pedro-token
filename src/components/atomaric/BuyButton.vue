<template>
    <a href="" target="_blank">
        <button class="token-button--buy" >
        BUY
    </button>
    </a>
</template>


<script setup>

</script>

<style lang="sass">
.token-button--buy
    display: inline-block
    color: white
    background-color: #f5bd03
    padding: 12px 24px
    border-radius: 8px
    border: 0
    transition: .3s
    &:hover, &:focus, &:active
        background-color: lighten(#f5bd03, 20%)
        cursor: pointer
</style>

