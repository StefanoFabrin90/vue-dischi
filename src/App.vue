<template>
  <div id="app">
    <!-- header -->
    <Header  @performSearch="searchMusic"/>

    <!-- main -->
    <main>
      <Sectioncard  :ListArtist="filteredListMusic"/>
    </main>
    


    
    
    
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Sectioncard from '@/components/Sectioncard.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Sectioncard,
  },
  data() {
      return {
        CardList: null,
        searchGenre: '',
      };
  },

  computed: {
    filteredListMusic() {
      if(this.searchGenre === '') {
        return this.CardList;
      }

      return this.CardList.filter(item => {
        return item.genre.includes(this.searchGenre)
      });
    },
  },
  created() {
      this.getCardList();
  },

  methods: {
      getCardList () {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')

        .then(result => {
          // console.log(result.data.response);
          this.CardList = result.data.response;
        })

        .catch (err => console.log(err));
      },

      searchMusic(value) {
        console.log(value);
        this.searchGenre = value;
      }
  },
}
</script>

<style lang="scss">
@import '@/styles/globals.scss';
</style>
