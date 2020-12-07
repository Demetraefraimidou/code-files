<template>
  <div class="home">
    <div class="row">
      <div v-for="article in articles" :key="article.title" class="col-sm-4">
        <div v-if="article.images[0].link.length === 0">
          <router-link :to="'/article/' + article.id"><img v-if="article.images.length > 0" :src="getImg(article.images[0].image)" width="40%"></router-link>
        </div>
        <div v-if="article.images[0].link.length > 0">
          <img class="linked-image" :src="getImg(article.images[0].image)" v-on:click="redirect(article.images[0].link)" width="40%">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import articles from '../assets/article.json'

export default {
  name: 'Home',
  components: {

  },
  data() {
    return {
      articles
    }
  },
  methods: {
    getImg(path) {
      return require('../assets/' + path);
    },
    redirect(path) {
      window.open(path, "_blank")
    }
  }
}
</script>

<style>

.home{
  font-size: 1.3rem;
  margin-top: 5%;
}

.linked-image {
  cursor: pointer;
}

</style>
