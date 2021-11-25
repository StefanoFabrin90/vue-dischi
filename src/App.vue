<template>
  <div id="app">
    <!-- header -->
    <Header />

    <!-- main -->
    <main>
      <Sectioncard />
    </main>
    


    
    
    
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Sectioncard from '@/components/Sectioncard.vue';



export default {
  name: 'App',
  components: {
    Header,
    Sectioncard,
  }
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
</style>
