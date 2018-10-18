<template>
  <section class="container">

    <lang-switcher></lang-switcher>

 <nuxt-link :to="$i18n.path('')" class="Header__Link" exact>
            {{ $t('links.home') }}
      </nuxt-link>

      <nuxt-link :to="$i18n.path('contact')" class="Header__Link" exact>
            {{ $t('links.contact') }}
            </nuxt-link>


<h1>{{$t('about.title')}}</h1>
<p>{{$t('about.introduction')}}</p>


  </section>
</template>

<script>
import Lang_switcher from '~/components/Lang_switcher.vue'

export default {
  components: {
    'lang-switcher': Lang_switcher
  },
  
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
#Header_Link{
  text-align : center;
}
</style>
