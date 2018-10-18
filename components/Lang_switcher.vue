<template>
  <section class="container">
    <el-button @click="changeLang('en')">English</el-button>
    <el-button @click="changeLang('gr')">Ελληνικά</el-button>







  </section>
</template>

<script>

export default {

  
  methods: {
    changeLang:function (lang) {
      //mutate 'locale' in store
      this.$store.commit('SET_LANG', lang)
      //re-route to the current page but with the selected language in a query string
      this.$i18n.locale = lang;
    }
  }
} 
</script>

<style>

</style>
