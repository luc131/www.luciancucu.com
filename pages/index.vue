
<template>
  <div>
    <div v-if="$fetchState.pending" key="pending" />
    <div v-else-if="$fetchState.error" key="error" />
    <div v-else key="success">
      <div class="bg-green-900">
        <h1 class="text-gray-200 text-left pl-3 md:pl-20 pt-10 text-3xl">
          <span class="font-semibold">Lucian Cucu</span>
        </h1>
        <h2 class="text-gray-300 underline text-left pl-3 md:pl-20 text-lg">
          Writer
        </h2>
        <h3 class="text-gray-200 text-left pl-3 md:pl-20 text-sm">
          Click the button below to see my europass profile!
        </h3>
        <a class="bg-green-100 text-green-700 font-bold py-1 px-3 rounded-full ml-16" href="https://europa.eu/europass/eportfolio/api/eprofile/shared-profile/3135c2a5-e69a-4316-8e2e-dfc2efabeecf?view=html" target="_blank">
          About me
        </a>
      </div>
      <div>
        <section>
          <div class="text-center decoration-clone bg-gradient-to-b from-green-900 to-green-500 text-gray-100 text-lg font-semi-bold">
            Blog
          </div>
          <div v-for="post in feed.items" :key="post.id">
            <PostPreview
              :id="post.id"
              :title="post.title"
              :preview-text="post.content_html"
              :postdate="post.date_published"
            />
          </div>
          <a id="top" class="bg-green-600 text-gray-200 font-bold py-1 px-3 rounded-full mx-auto prose lg:prose-xl">
            Back to top
          </a>
          <a href="#top" />
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
