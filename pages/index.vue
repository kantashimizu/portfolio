<template lang="pug">
section.main
  cursor-fx(color="#333333" color-hover="#acf98e")
  Opning
  Header(
    @changeMenu="changeMenu"
    :menuActive="pageActive"
  )
  About(v-if="pageActive.about")
  Works(v-if="pageActive.works")
  Contents(v-if="pageActive.contents")
</template>

<script>
import Opning from '@/components/Opning'
import Header from '@/components/Header'
import About from '@/components/About'
import Works from '@/components/Works'
import Contents from '@/components/Contents'

export default {
  components: {
    Opning,
    Header,
    About,
    Works,
    Contents
  },
  data() {
    return {
      opningEl: '',
      pageActive: {
        about: true,
        works: false,
        contents: false
      }
    }
  },
  mounted() {
    let el = document.querySelector('.opning')
    setTimeout(function() {
      el.remove()
    }, 5000)
  },
  methods: {
    changeMenu(key) {
      if (key === 'about') {
        this.pageActive.about = true
        this.pageActive.works = false
        this.pageActive.contents = false
      }
      if (key === 'works') {
        this.pageActive.about = false
        this.pageActive.works = true
        this.pageActive.contents = false
      }
      if (key === 'contents') {
        this.pageActive.about = false
        this.pageActive.works = false
        this.pageActive.contents = true
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
