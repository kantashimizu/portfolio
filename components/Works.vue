<template lang="pug">
section.works
  div.contents
    template(v-for="item in contents")
      div.content
        div.img_box
          img(:src="item.img")
          div.mask
        div.text_box
          p.title {{ item.title }}
          p.bold 担当
          p.text {{ item.position }}
          p.bold 使用技術
          p.text {{ item.skill }}
          p.bold 概要
          p.text {{ item.explanation }}
</template>

<script>
export default {
  data() {
    return {
      contents: [
        {
          id: 1,
          img: require("@/assets/img/img_1.png"),
          title: '某企業のHPコーディング',
          position: 'コーディング',
          skill: 'HTML/CSS/SCSS/Photoshop',
          explanation: '【副業】某企業のHPのレスポンシブコーディング全６ページを担当'
        },
        {
          id: 2,
          img: require("@/assets/img/img_2.png"),
          title: '多国語の音声翻訳SPA',
          position: '開発',
          skill: 'HTML/Pug/CSS/SASS/JavaScript/nuxt/XD',
          explanation: '【副業】車検時に必要な説明書を英語、中国語、韓国語、ポルトガル語で表示し各項目の説明を音声にて発声するSPA'
        },
        {
          id: 3,
          img: require("@/assets/img/img_3.png"),
          title: 'WordPressでのHP制作',
          position: '全般',
          skill: 'HTML/CSS/WordPress',
          explanation: '【副業】某事業のサービスHP。WordPressの導入から設定、コーディング全般を制作'
        }
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
.contents
  padding: 100px 80px 0
  display: flex
  justify-content: space-between
  .content
    width: 300px
.img_box
  width: 300px
  overflow: hidden
  position: relative
  img
    width: 100%
  .mask
    position: absolute
    top: 0
    opacity: 0
    height: 100%
    width: 100%
    background: black
.text_box
  margin-top: -2px
  transition: 1s
  background: $white
  width: 0%
  height: 280px
  p
    display: none
.img_box:hover ~ .text_box
  transition: 1s
  width: calc(100% - 20px)
  line-height: 1.2
  padding: 0 10px
  p
    display: block
    word-wrap: break-word
.img_box:hover img
  transition: 0.3s
  transform: scale(1.2, 1.2)
.img_box:hover .mask
  transition: 0.3s
  opacity: 0.3
.title
  padding-top: 10px
  text-align: center
  font-weight: bold
.bold
  font-weight: bold
  padding-top: 10px
.text
  padding-top: 5px
</style>


