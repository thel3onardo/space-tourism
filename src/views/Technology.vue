<template>
    <div class="technology">
        <NavBar/>
        <transition name="fade" appear>
        <div class="technology__content-container">
            <Header :page_number="'03'" :header_label="'space launch 101'"/>
            
            <div class="technology__content">
                <div class="technology__content__menu">
                    <TechnologyCircle :is_active="currentTechnologyItem === 1" :circle_number="1" @changetechitem="changeCurrentTechnologyItem"/>
                    <TechnologyCircle :is_active="currentTechnologyItem === 2" :circle_number="2"
                    @changetechitem="changeCurrentTechnologyItem"/>
                    <TechnologyCircle :is_active="currentTechnologyItem === 3" :circle_number="3"
                    @changetechitem="changeCurrentTechnologyItem"/>
                </div>

                <transition name="fade">
                    <TechnologyItem :item_title="'launch vehicle'" :item_description="`A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth's surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it's quite an awe-inspiring sight on the launch pad!`" :item_image="'image-launch-vehicle-portrait'" v-show="currentTechnologyItem === 1"/>
                </transition>

                <transition name="fade">
                    <TechnologyItem :item_title="'spaceport'" :item_description="`A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.`" :item_image="'image-spaceport-portrait'" v-show="currentTechnologyItem === 2"/>
                </transition>

                <transition name="fade">
                    <TechnologyItem :item_title="'space capsule'" :item_description="`A space capsule is an often-crewed spacecraft that uses a blunt-body reentry capsule to reenter the Earth's atmosphere without wings. Our capsule is where you'll spend your time during the flight. It includes a space gym, cinema, and plenty of other activities to keep you entertained.`" :item_image="'image-space-capsule-portrait'" v-show="currentTechnologyItem === 3"/>
                </transition>
            </div>
        </div>
        </transition>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import Header from '../components/Header.vue'
import TechnologyCircle from '../components/TechnologyCircle.vue'
import TechnologyItem from '../components/TechnologyItem.vue'

export default {
    name: 'Technology',
    data() {
        return {
            currentTechnologyItem: 1,
        }
    },
    components: {
        NavBar,
        Header,
        TechnologyCircle,
        TechnologyItem
    },
    methods: {
        changeCurrentTechnologyItem(number) {
            console.log('teste');
            console.log(number);
            return this.currentTechnologyItem = number;
        }
    }
}
</script>

<style lang="sass" scoped>
    .technology
        padding: 2em 0
        min-height: 100vh
        height: 100%
        width: 100%
        display: flex
        flex-direction: column

        background-image: url('../assets/technology/background-technology-desktop.jpg')
        background-size: cover
        background-position: center
        background-repeat: no-repeat

    .technology__content-container
        max-width: 1400px
        width: 100%
        margin: 0 auto

    .technology__content
        display: flex
        position: relative
        margin: 4em 0

    .technology__content__menu
        display: flex
        flex-direction: column
        justify-content: center

        height: 100%
        padding-right: 5%

    .technology__content-container
        padding-left: 10%

</style>