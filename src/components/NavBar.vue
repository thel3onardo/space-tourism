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
    @import '../sass/_variables.scss'

    @keyframes teste
        0%
            transform: rotate(0deg) scale(1)

        50%
            transform: rotate(180deg) scale(1.1)

        100%
            transform: rotate(359deg) scale(1)

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

            &:hover
                animation: teste 1.5s ease
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
            color: inherit
            height: 100%
            text-decoration: none
            margin: 0 1.5em
            border-bottom: 2px solid rgba(0, 0, 0, 0)

            display: flex
            align-items: center
            transition: all .5s ease
        
            &:hover
                border-bottom: 2px solid #fff
                color: $color_pale_blue

    .nav-link__number
        font-weight: 800
        margin-right: .4em
        letter-spacing: 2px
    
    .nav-link__name
        font-weight: 400
        text-transform: uppercase
        letter-spacing: 2px
        color: inherit

    @media screen and (max-width: 480px)
        .nav-bar__line
            display: none

    @media screen and (min-width: 768px)
        .nav-bar__line
            display: none
</style>