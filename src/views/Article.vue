<template>
  <div class="content">
    <div>
      <h1>{{ article.title }}</h1>
    </div>
    <img v-if="article.images.length > 0 && article.images[1].display" :src="getContent(article.images[1].image)" width="100%">
    <div v-for="paragraph in paragraphs" :key="paragraph">
      <!-- Display image -->
      <div v-if="paragraph.length === 1 && article.images.length > 0">
        <a :href="article.images[getIndex(paragraph)].link" target="_blank">
          <img :src="getContent(article.images[getIndex(paragraph)].image)" width="30%">
        </a>
      </div>
      <!-- Display title -->
      <div v-if="paragraph.length > 1 && paragraph.length < 4" class="margin-top-small">
        <h3>{{ paragraph }}</h3>
      </div>
      <!-- Display text -->
      <p v-if="paragraph.length > 3 && !isPdf(paragraph)">{{ paragraph }} </p>
      <div v-if="isPdf(paragraph)">
        <embed :src="getContent(paragraph)" type="application/pdf"   height="700px" width="500">
      </div>
    </div>
  </div>
</template>
<script>
  import articles from '../assets/article.json'

  export default {
    name: 'Article',
    props: ['id'],
    data() {
      return {
        articles,
        article: {},
        paragraphs: []
      }
    },
    beforeMount: function() {
      this.article = this.articles[this.id]
      this.paragraphs = this.articles[this.id].contents
    },
    methods: {
      getContent(path) {
        return require('../assets/' + path);
      },
      getIndex(text) {
        switch (text) {
          case "A":
            return 1;
          case "B":
            return 2;
          case "C":
            return 3;
          case "D":
            return 4;
          case "E":
            return 5;
          case "F":
            return 6;
          case "G":
            return 7;
          case "H":
            return 8;
          case "I":
            return 9;
          case "J":
            return 10;
          case "K":
            return 11;
          case "L":
            return 12;
        }
      },
      isPdf(path) {
        if (path.endsWith(".pdf")) {
          return true;
        }
        return false;
      }
    }
  }
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inconsolata:wght@300&display=swap');
.content {
  margin-top: 15px;
  font-weight: bold;
  font-family: 'Inconsolata', monospace;

  margin-left: 5%;
  margin-right: 5%;
}

.margin-top-small {
  margin-top: 35px;
}

</style>
