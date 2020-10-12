<template>
  <div>
    hello
    <h1>
      {{ lookslike.name }}
    </h1>
    <p>
      {{ lookslike.looks_like }}
    </p>
    <img :src="lookslike.photo_url" />
  </div>
</template>

<script>
import data from '../data.json';

export default {
  name: 'LooksLike',
  props: {
    name: String,
    description: String,
    image: String,
    year: String,
  },
  computed: {
    lookslike() {
      const collection = data.find(entries => entries.year === this.year);
      return collection.entries.find(entry => entry.id === this.$route.params.id);
    }
  }
}
</script>