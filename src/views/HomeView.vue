<script>
export default {
    data() {
        return {
            message: "Hello World! Welcome to VueJS"
        };
    },
}
</script>

<template>
    <div class="container">
      <div class="text-center">
        <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />
        <h1>{{ message }}</h1>
      </div>
    </div>
</template>

<style>
/* Add any component specific styles here */

.card_container{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 25px 10px;
}

.card_container img{
  width: 100%;
  height: 15vw;
  object-fit: cover;
}

.news_card{
  display: flex;
  flex-direction: column;
  background-color: white;
  border: 2px solid  gray;
  border-radius: 5px;
  box-shadow: 0 3px 5px  0;
  width: 300px;
  border-bottom-style: solid;
  border-bottom-width: thick;
  border-bottom-color: #09a073;
}

.card_details{
  padding: 15px;
  display: flex;
  flex-direction: column;
}
</style>