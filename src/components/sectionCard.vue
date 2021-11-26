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
    <div class="loading" v-else>
      <span>loading</span>
      <div class="loader loader--style1" title="0">
          <svg version="1.1" id="loader-1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
              width="150px" height="150px" viewBox="0 0 40 40" enable-background="new 0 0 40 40" xml:space="preserve">
              <path opacity="0.2" fill="red" d="M20.201,5.169c-8.254,0-14.946,6.692-14.946,14.946c0,8.255,6.692,14.946,14.946,14.946
              s14.946-6.691,14.946-14.946C35.146,11.861,28.455,5.169,20.201,5.169z M20.201,31.749c-6.425,0-11.634-5.208-11.634-11.634
              c0-6.425,5.209-11.634,11.634-11.634c6.425,0,11.633,5.209,11.633,11.634C31.834,26.541,26.626,31.749,20.201,31.749z"/>
              <path fill="#000" d="M26.013,10.047l1.654-2.866c-2.198-1.272-4.743-2.012-7.466-2.012h0v3.312h0
              C22.32,8.481,24.301,9.057,26.013,10.047z">
              <animateTransform attributeType="xml"
              attributeName="transform"
              type="rotate"
              from="0 20 20"
              to="360 20 20"
              dur="0.5s"
              repeatCount="indefinite"/>
              </path>
          </svg>
      </div>
    </div>
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

span {
  display: flex;
  justify-content: center;
  text-transform: uppercase;
  color: red;
  font-size: 3rem;
  font-weight: 800;
}

.loader {
  display: flex;
  justify-content: center;
}
</style>