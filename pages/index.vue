
<template>
  <div>
    <div v-if="$fetchState.pending" key="pending" />
    <div v-else-if="$fetchState.error" key="error" />
    <div v-else key="success">
      <div class="bg-green-900">
        <h1 class="text-white text-left pl-3 md:pl-20 pt-20 text-3xl">
          <span class="font-semibold">Lucian Cucu</span>
        </h1>
      </div>
      <div>
        <section>
          {{ feed.items }}
          <PostPreview
            v-for="post in feed.items"
            :id="post.id"
            :key="post.id"
            :title="post.title"
            :preview-text="post.content_html"
          />
        </section>
      </div>
    </div>
  </div>
</template>

<script>
import PostPreview from '@/components/Items/PostPreview.vue'

export default {
  components: {
    PostPreview
  },
  data () {
    return {
      feed: {}
    }
  },
  async fetch () {
    const url = 'https://api.revas.app/feeds/directories/blog-it/feed.json?public_key=01f9k40fwm4exjsptqd1gxhraw'
    const { data } = await this.$axios.get(url)
    this.feed = data
  }
}

</script>
