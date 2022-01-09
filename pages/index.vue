<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData({ $microcms }) {
    const data = await $microcms.get({
      endpoint: 'projects',
    });
    return data;
  }
}
</script>