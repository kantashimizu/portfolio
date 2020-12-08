<template lang="pug">
section.main
  Opning
  Header(
    @changeMenu="changeMenu"
    :menuActive="pageActive"
  )
  About(v-if="pageActive.about")
  Works(v-if="pageActive.works")
</template>

<script>
import Opning from '@/components/Opning'
import Header from '@/components/Header'
import About from '@/components/About'
import Works from '@/components/Works'

export default {
  components: {
    Opning,
    Header,
    About,
    Works
  },
  data() {
    return {
      opningEl: '',
      pageActive: {
        about: true,
        works: false
      }
    }
  },
  mounted() {
    let el = document.querySelector('.opning')
    setTimeout(function() {
      el.remove()
    }, 5000)
    return this.mouseStalker()
  },
  methods: {
    changeMenu(key) {
      if (key === 'about') {
        this.pageActive.about = true
        this.pageActive.works = false
      }
      if (key === 'works') {
        this.pageActive.about = false
        this.pageActive.works = true
      }
    }
  }
}
</script>

<style lang="sass" scoped>
.main
  height: 100vh
  background: $gray
</style>
