<template>
  <div id="app" class=" h-screen flex">

    <navigationMenu />

    <tweet />

    <searchFollow />

  </div>
</template>

<script>
import navigationMenu from './components/navigationMenu'
import tweet from './components/tweet'
import searchFollow from './components/searchFollow'
import './assets/tailwind.css'

export default {
  name: 'App',
  components: {
    navigationMenu,
    tweet,
    searchFollow,
  }
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.min.css';

</style>
