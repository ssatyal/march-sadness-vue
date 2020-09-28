<template>
  <div class="hello">
    <h1>March Sadness</h1>
    <h2>what famous people in sports look like</h2>
    <div v-for="(item, index) in names" :key="index">
      <p>{{item.name}}</p>
      <p>{{item.looks_like}}</p>
      <img :src='`${item.photo_url}`'/>
      <img>
    </div>
  </div>
</template>

<script>
import data from '../data.json'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  computed: {
    names() {
      const names = data['2015'].map(item => item);
      return names;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
