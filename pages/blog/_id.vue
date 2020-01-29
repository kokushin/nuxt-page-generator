<template>
  <article>
    <header>
      <h1>{{ blog.title }}</h1>
    </header>
    <main>
      <div v-html="blog.body" />
    </main>
    <footer>
      <p>Tag: {{ blog.tag }}</p>
      <time :datetime="blog.created_at">{{
        $dayjs(blog.created_at).format('YYYY.MM.DD')
      }}</time>
    </footer>
  </article>
</template>

<script>
export default {
  asyncData({ params }) {
    const fetchblog = () => {
      const blog = require(`~/db/blog.json`)
      return blog.items.filter((item) => {
        if (item.id === params.id) {
          return item
        }
      })
    }
    return {
      blog: fetchblog()[0]
    }
  }
}
</script>
