<template>
  <div class="container">
    <div v-if="CardList !== null" class="row">
      <div class="col-3 Listcard" v-for="(card, index) in CardList" :key="`card-${index}`">
        <!-- Card -->
        <Card 
          :image="card.poster"
          :title="card.title"
          :subTitle="card.author"
          :titleYear="card.year"
          :descrbition="card.genre"
        />
      </div>
    </div>
    <div v-else>loading</div>
  </div>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue'

export default {
    name: 'sectionCard',
    components: {
      Card,
    },

    data() {
      return {
        CardList: null,
      };
    },

    created() {
      this.getCardList();
    },

    methods: {
      getCardList () {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')

        .then(result => {
          console.log(result.data.response);
          this.CardList = result.data.response;
        })

        .catch (err => console.log(err));
      }
    }
}
</script>


<style scoped lang="scss">
.Listcard {
  padding: 1rem;
  margin-bottom: 1rem;
}
</style>