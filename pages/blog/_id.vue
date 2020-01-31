<template>
  <article>
    <header>
      <h1>{{ post.title }}</h1>
    </header>
    <main>
      <figure>
        <img :src="post.thumb" alt="" />
      </figure>
      <div v-html="post.body" />
    </main>
    <footer>
      <p>Tag: {{ post.tag }}</p>
      <time :datetime="post.created_at">{{
        $dayjs(post.created_at).format('YYYY.MM.DD')
      }}</time>
    </footer>
  </article>
</template>

<script>
export default {
  asyncData({ params }) {
    const fetchPosts = () => {
      const posts = require(`~/db/posts.json`)
      return posts.items.filter((post) => {
        if (post.id === params.id) {
          return post
        }
      })
    }
    return {
      post: fetchPosts()[0]
    }
  },
  head() {
    return {
      title: this.post.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.post.description
        },
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.post.title
        },
        {
          hid: 'og:description',
          property: 'og:description',
          content: this.post.description
        },
        {
          hid: 'og:image',
          property: 'og:image',
          content: this.post.thumb
        }
      ]
    }
  }
}
</script>
