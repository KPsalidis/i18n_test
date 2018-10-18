<template>
  <section class="container">


   <lang-switcher></lang-switcher>
   




<nuxt-link :to="$i18n.path('')" class="Header__Link" exact>
            {{ $t('links.home') }}
        </nuxt-link>

<nuxt-link :to="$i18n.path('about')" class="Header__Link" exact>
            {{ $t('links.about') }}
        </nuxt-link>


<h1>{{$t('contact.title')}}</h1>
<p>{{$t('contact.introduction')}}</p>


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

</style>
