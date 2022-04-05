<script>
import NewsList from '@/components/NewsList.vue'
export default {
    data() {
        return {
            message: "Hello World! Welcome to VueJS"
        };
    },
    components: { NewsList }
}
</script>

<template>
    <div class="container">
      <div class="text-center">
        <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
        <h1>{{ message }}</h1>
      </div>
      <NewsList />
    </div>
</template>

<style>
/* Add any component specific styles here */

.card_container{
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  grid-gap: 3rem;
  align-items: stretch;
}

.card_container img{
  width: 300px;
  height: 170px;
}

.card_container p {
}

.news_card{
  display: flex;
  flex-direction: column;
  background-color: white;
  border: 1px solid  gray;
  border-radius: 5px;
  box-shadow: none;
  transition: all 0.3s ease-in-out;
  padding-bottom: 20px;
  width: 300px
}

.card_details{
  padding: 15px;
  display: flex;
  flex-direction: column;
}
</style>