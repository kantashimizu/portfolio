<template lang="pug">
section.header
  p(
    :class="{ active: menuActive.about}"
    @click="menuClick('about')"
  ) About
  p(
    :class="{ active: menuActive.works}"
    @click="menuClick('works')"
  ) Works
  p(
    :class="{ active: menuActive.contents}"
    @click="menuClick('contents')"
  ) Contents
</template>

<script>
export default {
  name: 'Header',
  props: {
    menuActive: {
      type: Object,
      required: true,
    }
  },
  methods: {
    menuClick(key) {
      this.$emit('changeMenu', key)
    }
  }
}
</script>

<style lang="sass" scoped>
.header
  padding: 0 50px
  height: 80px
  text-align: rigth
  display: flex
  align-items: center
  justify-content: flex-end
  p
    margin-right: 20px
    font-size: 14px
.active
  font-weight: bold
</style>
