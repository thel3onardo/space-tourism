<template>
  <div id="app">
    <audio loop ref="audio">
      <source src="./audio/interstellar.mp3" type="audio/mpeg">
    </audio>
    <router-view/>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$refs.audio.volume = 0.5
    console.log(this.$refs.audio.volume)
  }
}
</script>

<style lang="scss">
  @import './sass/variables.scss';

  @import url('https://fonts.googleapis.com/css2?family=Bellefair&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Barlow+Condensed:ital,wght@0,100;0,200;0,300;0,400;1,100;1,200;1,300&family=Bellefair&display=swap');

  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    color: #ffffff;
    font-family: $text-texts;
  }

  ::-moz-selection { /* Code for Firefox */
    color: $color_dark;
    background: $color_white;
  }

  ::selection {
    color: $color_dark;
    background: $color_white;
  }

  body::-webkit-scrollbar {
    width: .8em;
  }

  body::-webkit-scrollbar-track {
    background-color: $color_dark
  }
  
  body::-webkit-scrollbar-thumb {
    background-color: $color_white;
    border-radius: 1px;
    filter: brightness(1.5);
    box-shadow: 0px 0px 30px rgba(255, 255, 255, 1);
  }

</style>
