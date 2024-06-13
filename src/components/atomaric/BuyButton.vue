<template>
    <a href="" target="_blank" class="token-button--buy">
        <button  >
        BUY
        </button>
    </a>
</template>


<script setup>

</script>

<style lang="sass">
a
    &.token-button--buy
        display: inline-block
        button
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

