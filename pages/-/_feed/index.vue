<template>
  <div class="post-page">
    <section class="post-list">
      <PostPreview
        v-for="post in feed.items"
        :id="post.id"
        :key="post.id"
        :title="post.title"
        :preview-text="post.content_html"
      />
    </section>
  </div>
</template>

<script>

export default {
  data () {
    return {
      feed: {},
      loadedPosts: [
        {
          id: 1,
          title: 'First Post',
          previewText: 'This is my first post'
        }
      ]
    }
  },
  async fetch () {
    const url = 'https://api.revas.app/feeds/directories/blog-it/feed.json?public_key=01f9k40fwm4exjsptqd1gxhraw'
    const { data } = await this.$axios.get(url)
    this.feed = data
  }
}

</script>
