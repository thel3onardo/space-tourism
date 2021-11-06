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
        position: fixed
        bottom: 1%
        left: 1%
        border-radius: 10px
        background-color: #181818
        cursor: pointer
        transition: all .5s ease

        display: flex
        justify-content: center
        align-items: center
        
        color: $color_white
        font-family: $text-titles

        &:hover
            transform: translateY(-7px)
</style>