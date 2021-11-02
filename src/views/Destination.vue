<template>
<transition name="fade">
  <div class="container">
      <NavBar/>

      <div class="destination">
          <div class="destination__title">
              <span>01</span>
              <span>pick your destination</span>
          </div>
          <div class="destination__content">
            <DestinationItem :title="'moon'" :description="'See our planet as you’ve never seen it before. A perfect relaxing trip away to help regain perspective and come back refreshed. While you’re there, take in some history by visiting the Luna 2 and Apollo 11 landing sites.'" :avg_distance="384" :travel_time="1" v-if="currentDestinationItem === 1" @change-destination-item="changeCurrentDestinationItem"/>

            <DestinationItem :title="'mars'" :description="'Don’t forget to pack your hiking boots. You’ll need them to tackle Olympus Mons, the tallest planetary mountain in our solar system. It’s two and a half times the size of Everest!'" :avg_distance="225" :travel_time="9" v-if="currentDestinationItem === 2" @change-destination-item="changeCurrentDestinationItem"/>

            <DestinationItem :title="'europa'" :description="'The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.'" :avg_distance="256" :travel_time="36" v-if="currentDestinationItem === 3" @change-destination-item="changeCurrentDestinationItem"/>

            <DestinationItem :title="'titan'" :description="'The only moon known to have a dense atmosphere other than Earth, Titan is a home away from home (just a few hundred degrees colder!). As a bonus, you get striking views of the Rings of Saturn.'" :avg_distance="256" :travel_time="84" v-if="currentDestinationItem === 4" @change-destination-item="changeCurrentDestinationItem"/>
          </div>
      </div>
  </div>
</transition>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import DestinationItem from '../components/DestinationItem.vue'

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

<style lang="scss" scoped>
    .fade-enter-active, .fade-leave-active {
    transition: opacity .5s
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    opacity: 0
    }
</style>

<style lang="sass" scoped>
    @import '../sass/variables.scss'

    .active
        color: #fff !important
        border-bottom: 3px solid $color_white !important

    .container
        height: 100%
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
        width: 80%
        height: 88.5%
        max-width: 1400px
        margin: 0 auto

    .destination__title
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