<template lang="pug">
section.opning
  div.name
    span k
    span a
    span n
    span t
    span a
    span p
    span o
    span r
    span t
    span f
    span o
    span l
    span i
    span o
</template>

<script>
export default {
  name: 'Opning'
}
</script>

<style lang="sass" scoped>
.opning
  position: fixed
  top: -50%
  left: -50%
  background: $white
  height: 200%
  width: 200%
  display: flex
  justify-content: center
  align-items: center
  letter-spacing: 0.4em
  font-size: 25px
  white-space: nowrap
  overflow: hidden
  transform:rotate(17deg) !important
  @include fadeInWordY(14)
  animation: topSlid 5s
  animation-fill-mode: forwards
.name
  transform: rotate(-17deg)
  animation: fontHidden 5s
  animation-fill-mode: forwards
@keyframes topSlid
  0%
    width: 200%
  50%
    width: 200%
  100%
    width: 0%
    display: none
@keyframes fontHidden
  0%
  50%
    opacity: 0.5
  60%
    opacity: 0.1
  100%
    opacity: 0
  </style>
