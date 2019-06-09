<template>
  <div>
      <div class="container">
          <div class="card" v-for="cardItem in cardItems" v-bind:key="cardItem.id">
            <img class="thumbnail" v-bind:src="cardItem.thumbnail" alt="">
            <h3 class="title">{{cardItem.title}}</h3>
            <p class="labels">{{cardItem.labels}}</p>
            <p class="description">{{cardItem.description}}</p>
            <a :href="cardItem.url">go to article</a>
          </div>
      </div>
  </div>
</template>

<script>
export default {
  data() {return {
    cardItems: []
  }},
  
  created: function(){
      this.$http.get('http://localhost:3000/items')
      .then(function(response){
          this.cardItems = response.data;
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a {
  color: #42b983;
  text-decoration: none;
}

.container {
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    grid-gap:0.5em;
    grid-auto-rows: minmax(100px, auto);
}

.thumbnail {
    width: 100%;
    display: block;
}

.title {
    margin: 0.5em 0 0.5em 0;
    font-size: 1.5em;
}

.labels {
    color: #F4AD3A;
    margin-top: 0.5em;
    margin-bottom: 0.5em;
}

.description {
    font-size: 1em;
    color: grey;
}

.card {
    border: 1px solid #F4AD3A;
    border-radius: 20px;
    background: white;
    padding: 1.5em;
    margin: 0.5em;
    padding-bottom: 10px;
}

@media(max-width: 900px){
    .container {
        grid-template-columns: repeat(2, 50%);
    }
}

@media(max-width: 700px){
    .container {
        grid-template-columns: repeat(1, 1fr);
    }
}
</style>