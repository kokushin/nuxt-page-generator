<template>
  <section>
    <article v-for="item in posts.items" :key="item.id">
      <nuxt-link :to="`/blog/${item.id}`">
        <h2>{{ item.title }}</h2>
        <p>Tag: {{ item.tag }}</p>
        <time :datetime="item.created_at">{{
          $dayjs(item.created_at).format('YYYY.MM.DD')
        }}</time>
      </nuxt-link>
    </article>
  </section>
</template>

<script>
export default {
  asyncData({ params }) {
    return {
      posts: require(`~/db/posts.json`)
    }
  }
}
</script>
