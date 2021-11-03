<template>
    <div class="crew-item">
        <div class="crew-item__text">
            <h1>{{ role }}</h1>
            <h3>{{ name }}</h3>
            <p>{{ description }}</p>
        </div>
        <div class="crew-item__img">
            <img :src="require(`../assets/crew/${imageName}.png`)">
        </div>
    </div>
</template>

<script>
export default {
    name: 'CrewItem',
    props: {
        imageName: {
            type: String,
            required: true,
        },
        role: {
            type: String,
            required: true,
        },
        name: {
            type: String,
            required: true,
        },
        description: {
            type: String,
            required: true,
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/_variables.scss'

    .crew-item
        display: flex
        align-items: end
        justify-content: space-around
        height: 100%

    .crew-item__text
        display: flex
        flex-direction: column
        width: 50%

        h1
            font-family: $text-titles
            font-weight: 400
            color: rgb(255, 255, 255, 0.5)
            text-transform: uppercase

        h3
            font-family: $text-titles
            font-size: 56px
            font-weight: 400
            margin: .5em 0
            text-transform: uppercase
            color: $color_white

        p
            width: 80%
            color: $color_pale_blue
            line-height: 32px
            font-size: 1.2rem

    .crew-item__img
        width: 41%
        height: 100%

        img
            max-height: 100%
            transform: scale(1.05) translateY(-10px)
</style>