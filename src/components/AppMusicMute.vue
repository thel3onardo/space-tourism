<template>
    <div class="music-mute" @click="changeIconAndMute">
        <font-awesome-icon :icon="currentIcon" size="1x"/>
    </div>
</template>

<script>
export default {
    name: 'AppMusicMute',
    data() {
        return {
            currentIcon: 'volume-up',
        }
    },
    methods: {
        changeIconAndMute() {
            console.log(`a`)
            if (this.currentIcon === 'volume-up') {
                this.currentIcon = 'volume-mute'
                this.$emit('changemusicstate', 'muted');
            } else {
                this.currentIcon = 'volume-up'
                this.$emit('changemusicstate', 'unmuted');
            }
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/_variables.scss'

    .music-mute
        height: 50px
        width: 50px
        border-radius: 10px
        background-color: #181818
        cursor: pointer
        margin: 1em
        transition: all .5s ease
        position: fixed
        bottom: 0
        
        color: $color_white
        font-family: $text-titles
        display: flex
        justify-content: center
        align-items: center

        &:hover
            transform: translateY(-7px)
</style>