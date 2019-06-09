<template>
  <div>
    <h1>Skillio</h1>
    <p>Team members:</p>
    <ul>
        <li v-for="(member, i ) in members" :key="i">{{member}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {return {
    members: []
  }},
  mounted(){
        fetch('http://localhost:3000/members')
        .then((response) => {
            return response.json()
        })
        .then((members) => {
            this.members = members
        })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  text-align: center;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>