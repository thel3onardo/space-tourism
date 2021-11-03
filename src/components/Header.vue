<template>
    <div class="header">
        <span>{{ page_number }}</span>
        <span>{{ header_label }}</span>
    </div>
</template>

<script>
export default {
    name: 'Header',
    props: {
        page_number: {
            type: String,
            required: true,
        },
        header_label: {
            type: String,
            required: true
        }
    }
}
</script>

<style lang="sass" scoped>
    .header
        font-size: 1.8rem

        span:first-child
            color: rgba(255, 255, 255, 0.25)
            font-weight: 600
            margin: 0 1em

        span
            color: #color_white
            text-transform: uppercase
            letter-spacing: 4.72px
</style>