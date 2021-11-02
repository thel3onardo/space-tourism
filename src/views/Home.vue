<template>
    <div class="home">
      <NavBar/>

      <div class="home-content">
        <div class="home-content__text">
          <h3>so you want to travel to</h3>
          <h1>space</h1>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Expedita dolorum doloribus cum sit? Explicabo distinctio dolorum iusto quo nam voluptatibus provident, ex possimus excepturi, quibusdam officiis est numquam! Suscipit, quisquam?</p>
        </div>
        <div class="home-content__button">
            <button>explore</button>
        </div>
      </div>
    </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

import NavBar from '../components/NavBar.vue';

export default {
  name: 'Home',
  components: {
    NavBar,
  }
};

</script>

<style lang="sass">
    @import '../sass/variables.scss'

    .home
      height: 100%
      min-height: 100vh
      width: 100%

      background-image: url('../assets/home/background-home-desktop.jpg')
      background-position: center
      background-repeat: no-repeat
      background-size: cover

      padding: 2em 0

    .home-content
      display: flex
      max-width: 1400px
      height: 88.5%
      margin: 0 auto
      justify-content: space-around
      align-items: center

    .home-content__text
      max-width: 450px
      
      h3
        font-size: 28px
        font-weight: 300
        text-transform: uppercase
        letter-spacing: 5px

      h1
        font-size: 150px
        font-family: $text-titles
        font-weight: 400
        text-transform: uppercase
        margin: .1em 0

      p
        font-size: 1.2rem
        font-weight: 200
        line-height: 32px

    .home-content__button
      button
        color: $color_dark
        background-color: #fff
        width: 274px
        height: 274px
        border: none
        border-radius: 50%
        position: relative
        
        font-family: $text-titles
        font-size: 2rem
        text-transform: uppercase
        
        &:before
          content: ''
          position: absolute
          top: 0
          left: 0
          width: 100%
          height: 100%
          border-radius: 50%
          background-color: rgb(255, 255, 255, 0.1)
          transition: all .75s ease

        &:hover:before
          transform: scale(1.4)
</style>