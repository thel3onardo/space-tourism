<template>
    <div class="item">
        <div class="item__img">
            <img :src="require(`../assets/destination/image-${title}.png`)">
        </div>
        
        <div class="item-text">
            <nav>
                <button :class="{active: title === 'moon'}" @click="changeDestinationItem(1)">moon</button>
                <button :class="{active: title === 'mars'}" @click="changeDestinationItem(2)">mars</button>
                <button :class="{active: title === 'europa'}" @click="changeDestinationItem(3)">europa</button>
                <button :class="{active: title === 'titan'}" @click="changeDestinationItem(4)">titan</button>
            </nav>

            <h2>{{ title }}</h2>
            <p class="item-text__description">{{ description }}</p>
            <div class="item-text__line"> </div>

            <div class="item-details">
                <div>
                    <p>avg. distance</p>
                    <p>{{ transformDistance(avg_distance) }}</p>
                </div>
                <div>
                    <p>est. travel time</p>
                    <p>{{ transformTravelTime(travel_time) }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DestinationItem',
    props: {
        title: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        },
        avg_distance: {
            type: Number,
            required: true
        },
        travel_time: {
            type: Number,
            required: true
        }
    },
    methods: {
        transformDistance(distance) {
            return `${distance} MIL. KM`
        },
        transformTravelTime(travelTime) {
            if (travelTime > 12) {
                const years = travelTime / 12

                return `${years} YEARS`;
            }
            return `${travelTime} MONTHS`
        },
        changeDestinationItem(number) {
            this.$emit('change-destination-item', number)
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/variables.scss'

    .item
        display: flex
        width: 100%
    
    .item__img
        padding-right: 12em
    
    .item-text
        width: 100%
        font-size: 1rem

        h2
            font-size: 100px
            font-weight: 400
            text-transform: uppercase
            font-family: $text-titles
            margin-bottom: .10em

        nav
            margin-bottom: 2em

            button
                border: none
                background: none
                font-size: 1rem
                line-height: 19.2px
                letter-spacing: 2.7px
                text-transform: uppercase
                color: $color_pale_blue
                margin-right: 2em
                padding: .8em 0
                cursor: pointer
                transition: all .5s

                &:hover
                    color: $color_white

    .item-text__description
        font-size: 1.25rem
        font-weight: 300
        line-height: 32px
        color: $color_pale_blue
        padding-bottom: 1.5em

    .item-text__line
        width: 100%
        height: 1px
        position: relative
        margin: 1em 0

        &:before
            content: ''
            position: absolute
            left: 0
            top: 0
            width: 100%
            height: 100%
            background-color: #383B4B

    .item-details
        display: flex
        justify-content: space-between
        width: 80%

        p:first-child
            font-size: 0.9rem
            letter-spacing: 2.36px
            text-transform: uppercase
            color: $color_pale_blue
            font-family: $text-texts

        p
            font-size: 1.8rem
            font-family: $text-titles
            margin: .4em 0
</style>