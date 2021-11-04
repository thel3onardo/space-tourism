<template>
    <div class="crew">
        <NavBar/>

        <div class="crew-content">
            <Header :page_number="'02'" :header_label="'meet your crew'" @changecrew="listeningChangeCrew"/>

            <transition name="fade">
                <CrewItem :name="'douglas hurley'" :description="'Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.'" :role="'commander'" :image-name="'image-douglas-hurley'"
                :current_crew="currentCrew" 
                @changecrew="listeningChangeCrew" v-show="currentCrew === 1"/>
            </transition>

            <transition name="fade">
                <CrewItem :name="'mark shuttleworth'" :description="'Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.'" :role="'mission specialist'" :image-name="'image-mark-shuttleworth'"
                :current_crew="currentCrew" @changecrew="listeningChangeCrew" v-show="currentCrew === 2"/>
            </transition>
            <transition name="fade">
                <CrewItem :name="'victor glover'" :description="'Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer.'" :role="'pilot'" :image-name="'image-victor-glover'"
                :current_crew="currentCrew"  @changecrew="listeningChangeCrew" v-show="currentCrew === 3"/>
            </transition>
            <transition name="fade">
                <CrewItem :name="'anousheh'" :description="'Anousheh Ansari is an Iranian American engineer and co-founder of Prodea Systems. Ansari was the fourth self-funded space tourist, the first self-funded woman to fly to the ISS, and the first Iranian in space.'" :role="'flight engineer'" :image-name="'image-anousheh-ansari'"
                :current_crew="currentCrew"  @changecrew="listeningChangeCrew" v-show="currentCrew === 4"/>
            </transition>
        </div>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import Header from '../components/Header.vue'
import CrewItem from '../components/CrewItem.vue'

export default {
    name: 'Crew',
    data() {
        return {
            currentCrew: 1
        }
    },
    components: {
        NavBar,
        Header,
        CrewItem
    },
    methods: {
        listeningChangeCrew(value) {
            console.log(`mudeiiii - ${value}`)
            this.currentCrew = value;
        }
    }
}
</script>

<style lang="scss" scoped>
    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
    }
</style>

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
        position: relative
</style>