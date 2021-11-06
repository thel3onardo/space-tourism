<template>
    <div class="technology">
        <NavBar/>
        
        <div class="technology__content-container">
            <Header :page_number="'03'" :header_label="'space launch 101'"/>
            
            <div class="technology__content">
                <div class="technology__content__menu">
                    <TechnologyCircle :is_active="true" :circle_number="1"/>
                    <TechnologyCircle :is_active="false" :circle_number="2"/>
                    <TechnologyCircle :is_active="false" :circle_number="3"/>
                </div>
                <TechnologyItem :item_title="'launch vehicle'" :item_description="`A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth's surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it's quite an awe-inspiring sight on the launch pad!`" :item_image="'image-launch-vehicle-portrait'" v-if="false"/>

                <TechnologyItem :item_title="'spaceport'" :item_description="`A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.`" :item_image="'image-space-capsule-portrait'"/>
            </div>
        </div>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import Header from '../components/Header.vue'
import TechnologyCircle from '../components/TechnologyCircle.vue'
import TechnologyItem from '../components/TechnologyItem.vue'

export default {
    name: 'Technology',
    components: {
        NavBar,
        Header,
        TechnologyCircle,
        TechnologyItem
    }
}
</script>

<style lang="sass" scoped>
    .technology
        padding: 2em 0
        height: 100vh
        width: 100%
        display: flex
        flex-direction: column

        background-image: url('../assets/technology/background-technology-desktop.jpg')
        background-size: cover
        background-position: center
        background-repeat: no-repeat

    .technology__content-container
        max-width: 1400px
        margin: 0 auto

    .technology__content
        display: flex
        align-items: center
        height: 99%

    .technology__content__menu
        display: flex
        flex-direction: column
        padding-right: 5%

    .technology__content-container
        height: 85%
        padding-left: 10%

</style>