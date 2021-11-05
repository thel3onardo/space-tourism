<template>
    <div class="technology">
        <NavBar/>
        
        <div>
            <Header :page_number="'03'" :header_label="'space launch 101'"/>
            
            <div class="technology-content">
                <div class="technology-content__menu">
                    <TechnologyCircle :is_active="true" :circle_number="1"/>
                    <TechnologyCircle :is_active="false" :circle_number="2"/>
                    <TechnologyCircle :is_active="false" :circle_number="3"/>
                </div>
                <!-- item will come here -->
            </div>
        </div>
    </div>
</template>

<script>
import NavBar from '../components/NavBar.vue'
import Header from '../components/Header.vue'
import TechnologyCircle from '../components/TechnologyCircle.vue'

export default {
    name: 'Technology',
    components: {
        NavBar,
        Header,
        TechnologyCircle
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

    .technology__content
        display: flex

    .technology-content__menu
        display: flex
        flex-direction: column

</style>