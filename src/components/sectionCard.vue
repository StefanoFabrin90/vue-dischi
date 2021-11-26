<template>
  <div class="container">
    <div v-if="ListArtist !== null" class="row">
      <div class="col-3 Listcard" v-for="(card, index) in ListArtist" :key="`card-${index}`">
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

import Card from '@/components/Card.vue'

export default {
    name: 'sectionCard',
    components: {
      Card,
    },
    props: {
      ListArtist: Array
    }

    
}
</script>


<style scoped lang="scss">
.Listcard {
  padding: 1rem;
  margin-bottom: 1rem;
}
</style>