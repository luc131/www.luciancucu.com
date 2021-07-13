
<template>
  <div>
    <div v-if="$fetchState.pending" key="pending" />
    <div v-else-if="$fetchState.error" key="error" />
    <div v-else key="success">
      <div class="bg-green-900">
        <h1 class="text-white text-left pl-3 md:pl-20 pt-20 text-3xl">
          <span class="font-semibold">Lucian Cucu</span>
        </h1>
      <h2 class="text-white text-left pl-3 md:pl-20 text-base">Blogger</h2>
      <button type="submit" class="bg-white text-green-700 font-bold py-1 px-3 rounded-full ml-16" href="https://europa.eu/europass/eportfolio/api/eprofile/shared-profile/3135c2a5-e69a-4316-8e2e-dfc2efabeecf?view=html" target="_blank">
        About me
      </button>
        </div>
        <div>
        <section>
          <div class="text-center text-3xl text-green-700">
            Blog
          </div>
          <div>
            <PostPreview
              v-for="post in feed.items"
              :id="post.id"
              :key="post.id"
              :title="post.title"
              :preview-text="post.content_html"
            />
          </div>
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
