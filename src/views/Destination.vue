<template>
  <div class="container">
      <NavBar/>
      <transition name="fade" appear>
        <Header :page_number="'01'" :header_label="'Pick your destination'" class="header__style"/>
      </transition>
        <transition name="fade" appear>
        <div class="destination">
            <div class="destination__content">
                <DestinationItem :title="'moon'" :description="'See our planet as you’ve never seen it before. A perfect relaxing trip away to help regain perspective and come back refreshed. While you’re there, take in some history by visiting the Luna 2 and Apollo 11 landing sites.'" :avg_distance="384" :travel_time="1" v-if="currentDestinationItem === 1" @change-destination-item="changeCurrentDestinationItem"/>

                <DestinationItem :title="'mars'" :description="'Don’t forget to pack your hiking boots. You’ll need them to tackle Olympus Mons, the tallest planetary mountain in our solar system. It’s two and a half times the size of Everest!'" :avg_distance="225" :travel_time="9" v-if="currentDestinationItem === 2" @change-destination-item="changeCurrentDestinationItem"/>

                <DestinationItem :title="'europa'" :description="'The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.'" :avg_distance="256" :travel_time="36" v-if="currentDestinationItem === 3" @change-destination-item="changeCurrentDestinationItem"/>

                <DestinationItem :title="'titan'" :description="'The only moon known to have a dense atmosphere other than Earth, Titan is a home away from home (just a few hundred degrees colder!). As a bonus, you get striking views of the Rings of Saturn.'" :avg_distance="256" :travel_time="84" v-if="currentDestinationItem === 4" @change-destination-item="changeCurrentDestinationItem"/>
            </div>
        </div>
        </transition>
  </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import DestinationItem from '../components/DestinationItem.vue'
import Header from '../components/Header.vue'

export default {
    name: 'Destination',
    data() {
        return {
            currentDestinationItem: 1,
        }
    },
    components: {
        NavBar,
        DestinationItem,
        Header
    },
    methods: {
        changeCurrentDestinationItem(number) {
            console.log('rcebi');
            this.currentDestinationItem = number;

            console.log(this.currentDestinationItem);
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/variables.scss'

    .header__style
        margin: 0 auto
        width: 80%
        max-width: 1400px

    .active
        color: #fff !important
        border-bottom: 3px solid $color_white !important

    .container
        min-height: 100vh
        width: 100%
        padding: 2em 0

        background-image: url('../assets/destination/background-destination-desktop.jpg')
        background-position: center
        background-size: cover
        background-repeat: no-repeat

    .destination
        display: flex
        flex-direction: column
        justify-content: center
        align-items: center
        width: 80%
        min-height: calc(100vh - 64px)
        height: 100%
        max-width: 1400px
        margin: 0 auto
</style>