<template>
  <div>hello {{foo}}</div>
  <div v-for="item in yearEntries" :key="item.photo_url">
    <p>{{item.name}}</p>
    <p>{{item.looks_like}}</p>
    <router-link
      :to="`/${year}/lookslike/${item.id}`"
      :description="item.looks_like"
      :name="item.name"
      :image="item.photo_url"
      :year="year">
      <img :src='`${item.photo_url}`'/>
    </router-link>
  </div>
</template>

<script>
import data from '../data.json'
export default {
  name: 'Year',
  props: {
    entries: Array,
    year: String,
    foo: String,
  },
  computed: {
    yearEntries() {
      return data.filter(item => item.year === this.$route.params.year)[0].entries
    }
  },
}
</script>