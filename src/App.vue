<template>
  <div id="app">
    <router-view/>
  </div>
</template>

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
</style>
