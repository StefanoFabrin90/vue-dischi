<template>
  <div id="app">
    <!-- header -->
    <Header />

    <!-- main -->
    <main>
      <!-- section-card -->
      <sectionCard />
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import sectionCard from '@/components/sectionCard.vue';



export default {
  name: 'App',
  components: {
    Header,
    sectionCard,
  }
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
</style>
