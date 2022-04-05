<template>
    <div v-for="article in articles" class="card_container">
        <div class="news_card">
            <img :src="article.urlToImage" alt="news">
            <div class="card_details">
                <h6>{{ article.title }}</h6>
                <p class="card-text">{{ article.description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            articles: []
        }
    },
    created() {
        let self = this;
        fetch('https://newsapi.org/v2/top-headlines?country=us', 
{
    headers: {
        'Authorization': `Bearer ${import.meta.env.VITE_NEWSAPI_TOKEN}`
    }
})
    .then(function(response) {
        return response.json();
    })
    .then(function(data) {
        console.log(data);
        self.articles = data.articles;
    });
 }
};
</script>