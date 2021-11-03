<template>
    <div class="crew">
        <NavBar/>

        <div class="crew-content">
            <Header :page_number="'02'" :header_label="'meet your crew'"/>

            <CrewItem :name="'douglas hurley'" :description="'Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.'" :role="'commander'" :image-name="'image-douglas-hurley'" v-if="true"/>

            <CrewItem :name="'mark shuttleworth'" :description="'Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.'" :role="'mission specialist'" :image-name="'image-mark-shuttleworth'" v-if="false"/>

            <CrewItem :name="'victor glover'" :description="'Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer.'" :role="'pilot'" :image-name="'image-victor-glover'" v-if="false"/>
        </div>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import Header from '../components/Header.vue'
import CrewItem from '../components/CrewItem.vue'

export default {
    components: {
        NavBar,
        Header,
        CrewItem
    }
}
</script>

<style lang="sass">
    .crew
        height: 100vh
        width: 100%
        padding: 2em 0
        
        background-image: url('../assets/crew/background-crew-desktop.jpg')
        background-position: center
        background-size: cover

    .crew-content
        width: 80%
        height: 83%
        max-width: 1400px
        margin: 0 auto
</style>