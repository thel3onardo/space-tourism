<template>
    <div class="crew-item">
        <div class="crew-item__text">
            <h1>{{ role }}</h1>
            <h3>{{ name }}</h3>
            <p>{{ description }}</p>
            <div class="circles">
                <div class="circle" :class="{'circle__active': current_crew === 1}" @click="emitChangeCrew(1)"> </div>
                <div class="circle" :class="{'circle__active': current_crew === 2}" @click="emitChangeCrew(2)"> </div>
                <div class="circle" :class="{'circle__active': current_crew === 3}" @click="emitChangeCrew(3)"> </div>
                <div class="circle" :class="{'circle__active': current_crew === 4}" @click="emitChangeCrew(4)"> </div>
            </div>
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
        },
        current_crew: {
            type: Number,
            required: false,
        }
    },
    methods: {
        emitChangeCrew(value) {
            this.$emit('changecrew', value);
            console.log(event)
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/_variables.scss'

    .crew-item
        display: flex
        align-items: center
        justify-content: space-around
        height: 100%
        position: absolute

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
            margin: .3em 0
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

    .circles
        display: flex
        margin-top: 5em

    .circle
        width: 15px
        height: 15px
        margin-right: 1em
        border-radius: 50%
        background-color: rgba(255, 255, 255, 0.17)
        cursor: pointer
        transition: background-color .5s ease

        &:hover
            background-color: #fff

    .circle__active
        background-color: #fff
</style>