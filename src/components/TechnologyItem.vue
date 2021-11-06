<template>
    <div class="tech-item">
        <div class="tech-item__text">
            <span>the terminology</span>
            <h1>{{ item_title }}</h1>
            <p>{{ item_description }}</p>
        </div>
        <div class="tech-item__image">
            <img :src="require(`../assets/technology/${item_image}.jpg`)">
        </div>
    </div>
</template>

<script>
export default {
    props: {
        item_title: {
            type: String,
            required: true
        },
        item_description: {
            type: String,
            required: true
        },
        item_image: {
            type: String,
            required: true
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '@/sass/_variables.scss'

    .tech-item
        height: 100%
        width: 100%
        
        display: flex
        justify-content: space-between
        align-items: center
        position: absolute
        width: 90%
        height: 100%
        margin-left: 10%

    .tech-item__text
        width: 50%

        span
            font-size: 1rem
            line-height: 19.2px
            color: $color_pale_blue
            text-transform: uppercase
            letter-spacing: 2.7px

        h1
            margin: .2em 0
            color: $color_white
            font-family: $text-titles
            font-size: 56px
            font-weight: 400
            text-transform: uppercase

        p
            color: $color_pale_blue
            line-height: 32px
            font-size: 1.1rem

    .tech-item__image
        img
            max-height: 500px
            height: 100%
            width: 100%
            object-fit: cover
</style>