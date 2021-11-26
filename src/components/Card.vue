<template>
        <div class="card h-100">  
            <img :src="image" alt="">
            <h4>{{ title }}</h4>
            <h6>{{ subTitle }}</h6>
            <h6>{{ titleYear }}</h6>
            <p>{{ descrbition }}</p>
        </div>
        
</template>

<script>
export default {
 name: 'Card',
 props: {
     image: String,
     title: String,
     subTitle: String,
     titleYear: String,
     descrbition: String,
 },

};
</script>

<style scoped lang="scss">
.card {
  background-color: #2e3a46;
  margin: 1rem;
  text-align: center;
  padding: 1rem;

  img {
    margin-bottom: 2rem;
  }

  h4,h6,p {
    background-color: #2e3a46;
  }

  h4 {
    font-size: 18px;
    text-transform: uppercase;
  }
  h6 {
    color: #787c82;
    padding: 10px 0;
  }
}
</style>