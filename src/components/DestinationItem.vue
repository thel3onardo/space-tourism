<template>
    <div class="item">
        <div class="item__img">
            <img src="../assets/destination/image-europa.png" v-once>
        </div>
        
        <div class="item-text">
            <nav>
                <a href="">moon</a>
                <a href="">mars</a>
                <a href="">europa</a>
                <a href="">titan</a>
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
        }
    }
}
</script>

<style lang="sass">
    @import '../sass/variables.scss'

    .item
        display: flex
        width: 100%
        margin: 6em 0
    
    .item__img
        padding: 0 6em
    
    .item-text
        width: 100%
        font-size: 1rem

        h2
            font-size: 100px
            font-weight: 400
            text-transform: uppercase
            font-family: $text-titles
            margin-bottom: .10em

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