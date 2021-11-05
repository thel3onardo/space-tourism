<template>
  <div class="technology-circle" :class="{'is-active': is_active}">
      <span>{{ circle_number }}</span>
  </div>
</template>

<script>
export default {
    name: 'TechnologyCircle',
    props: {
        circle_number: {
            type: Number,
            required: true,
        },
        is_active: {
            type: Boolean,
            required: false,
        }
    }
}
</script>

<style lang="sass" scoped>
    @import '../sass/_variables.scss'

    .technology-circle
        font-family: $text-titles
        background: none
        height: 80px
        width: 80px
        border-radius: 50%
        border: 1px solid rgba(255, 255, 255, 0.25)
        margin-bottom: 2em
        color: #fff
        cursor: pointer

        transition: border .5s ease

        display: flex
        justify-content: center
        align-items: center

        &:hover
            border: 1px solid rgba(255, 255, 255)

        span
            color: inherit
            font-size: 2.5rem

    .is-active
        background-color: #fff
        color: $color_dark
</style>