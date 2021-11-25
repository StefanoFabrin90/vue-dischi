<template>
  <div class="container">
    <div v-if="CardList !== null" class="row">
      <div class="col-2 card" v-for="(card, index) in CardList" :key="`card-${index}`">
        <img :src="card.poster" alt="">
          <h4>{{ card.title }}</h4>
          <h6>{{ card.author }}</h6>
          <h6>{{ card.year }}</h6>
          <p>{{ card.genre }}</p>
      </div>
    </div>
    <div v-else>loading</div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'sectionCard',

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
.card {
  background-color: #2e3a46;
  margin: 1rem;
  padding: 1.5rem;
  text-align: center;

  img {
    margin-bottom: 2rem;
  }

  h4,h6,p {
    background-color: #2e3a46;
  }

  h4 {
    font-size: 20px;
    text-transform: uppercase;
  }
  h6 {
    color: #787c82;
    padding: 10px 0;
  }
}
</style>