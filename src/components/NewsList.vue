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

    <form @submit.prevent="searchNews" class="d-flex flex-column justify-content-center">
        <div class="input-group mx-sm-3 mb-2">
            <label class="visually-hidden" for="search">Search</label>
            <input type="search" name="search" v-model="searchTerm" 
                id="search" class="form-control mb-2 mr-sm-2" placeholder="Enter search term here" />
            <button class="btn btn-primary mb-2">Search</button>
        </div>
        <p>You are searching for {{ searchTerm }}</p>
    </form>
</template>

<script>
export default {
    data() {
        return {
            articles: []
        }
    },
    methods: {
        searchNews() {
        let self = this;
    fetch('https://newsapi.org/v2/everything?q='+ self.searchTerm + '&language=en', {
        headers: {
            'Authorization': `Bearer ${import.meta.env.VITE_NEWSAPI_TOKEN}`, 
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
    }   
};
</script>