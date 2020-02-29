<template lang="pug">
  .wrapper
    section.hero
      h1.hero__title Codigo
      h2.hero__subtitle A beautiful Markdown editor and note-taking app made for programmers.

    section.download
      a.download__button(:href="`https://github.com/alfonzm/codigo-app/releases/download/v${version}/Codigo-${version}.dmg`")  Download for Mac (v{{ version }})

    section.demo
      video.demo__video(
        autoplay
        playsinline
        muted
        loop
      )
        source(
          src="~/assets/demo.mp4"
          type="video/mp4"
          ref="demoVideo"
        )
    footer.footer
      span © {{ new Date().getFullYear() }}. Made by Alfonz Montelibano.
</template>

<script>

export default {
  data () {
    return {
      version: '1.0.0',
    }
  },
  mounted () {
    this.$refs.demoVideo.playbackRate = 2
  },
}
</script>

<style lang="sass">

@import url('https://fonts.googleapis.com/css?family=Inconsolata:400,700&display=swap')
$primaryBlack: #333
$secondaryBlack: #999

.wrapper
  @apply tw-mx-auto tw-w-full
  font-family: 'Inconsolata', sans-serif
  color: $primaryBlack

  @media (min-width: 576px)
    max-width: 576px
  @media (min-width: 768px)
    max-width: 768px
  @media (min-width: 992px)
    max-width: 992px
  @media (min-width: 1200px)
    max-width: 1200px

.hero
  @apply tw-mx-4 tw-mt-20 tw-mb-8 tw-text-center

  &__title
    @apply tw-font-bold
    font-size: 60pt

  &__subtitle
    @apply tw-text-xl tw-mx-auto
    font-weight: 300
    color: $secondaryBlack

.download
  @apply tw-mx-4 tw-text-center tw-mb-10

  &__button
    @apply tw-py-4 tw-mx-auto
    @apply tw-border
    border-color: $primaryBlack
    display: block
    max-width: 280px

    background: linear-gradient(to right, #333 50%, white 50%)
    background-size: 200% 100%
    background-position: right bottom
    transition: all .3s ease-out

    &:hover
      @apply tw-text-white tw-shadow
      background-position: left bottom

.demo
  @apply tw-mb-10

  &__video
    @apply tw-mx-auto tw-border tw-border-gray-300 tw-shadow-lg tw-outline-none
    pointer-events: none

.footer
  @apply tw-mx-4 tw-my-10 tw-text-center
  color: $secondaryBlack
</style>
