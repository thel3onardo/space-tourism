<template>
    <div class="nav-bar">
        <div class="nav-bar__image">
            <img src="../assets/shared/logo.svg" v-once>
        </div>

        <div class="nav-bar__line">
        </div>

        <nav>
            <router-link to="/">
                <span class="nav-link__number">00</span>
                <span class="nav-link__name">home</span>
            </router-link>

            <router-link to="/destination">
                <span class="nav-link__number">01</span>
                <span class="nav-link__name">destination</span>
            </router-link>

            <router-link to="/crew">
                <span class="nav-link__number">02</span>
                <span class="nav-link__name">crew</span>
            </router-link>

            <router-link to="/technology">
                <span class="nav-link__number">03</span>
                <span class="nav-link__name">technology</span>
            </router-link>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'NavBar'
}
</script>

<style lang="sass" scoped>
    @import '../sass/variables.scss'

    .nav-bar
        display: flex
        align-items: center
        justify-content: space-between
        height: 96px
        width: 100%
        max-width: 1400px
        margin: 0 auto

    .nav-bar__image
        padding-left: 3em
        img
            width: 48px

    .nav-bar__line
        position: relative
        width: 473px

        &:before
            content: ' '
            position: absolute
            width: 100%
            height: 1px
            background-color: #979797
            left: 55px
            z-index: 1

    nav
        height: 100%
        width: 55%
        background-color: rgb(151, 151, 151, 0.04)
        backdrop-filter: blur(12px)

        display: flex
        justify-content: center
        align-items: center

        a
            height: 100%
            text-decoration: none
            margin: 0 1.5em

            display: flex
            align-items: center
        
            &:hover
                border-bottom: 2px solid #fff

    .nav-link__number
        font-weight: 800
        margin-right: .4em
        letter-spacing: 2px
    
    .nav-link__name
        font-weight: 400
        text-transform: uppercase
        letter-spacing: 2px
</style>