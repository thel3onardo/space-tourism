<template>
  <div class="container">
      <NavBar/>

      <div class="destination">
          <div class="destination__title">
              <span>01</span>
              <span>pick your destination</span>
          </div>
          <div class="destination__content">
              <DestinationItem :title="'europa'" :description="'The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.'" :avg_distance="256" :travel_time="36"/>
          </div>
      </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import DestinationItem from '../components/DestinationItem.vue'

export default {
    name: 'Destination',
    components: {
        NavBar,
        DestinationItem,
    }
}
</script>

<style lang="sass">
    @import '../sass/variables.scss'

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