
<template>
  <div>
    <div v-if="$fetchState.pending" key="pending" />
    <div v-else-if="$fetchState.error" key="error" />
    <div v-else key="success">
      <a id="top" />
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
        <a class="md:w-32 lg:w-48 bg-green-100 text-green-700 font-bold py-1 px-3 rounded-full ml-16" href="https://europa.eu/europass/eportfolio/api/eprofile/shared-profile/3135c2a5-e69a-4316-8e2e-dfc2efabeecf?view=html" target="_blank">
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
          <a class="bg-green-100 text-green-700 font-bold py-1 px-3 rounded-full mx-auto prose lg:prose-xl ml-10" href="#top">Back to top</a>
        </section>
      </div>
    </div>
    <footer class="decoration-clone bg-gradient-to-b from-green-800 to-green-600">
      <p class="mx-auto lg:prose-base text-center text-gray-200">
        Author: Lucian Cucu
      </p>
      <p class="mx-auto lg:prose-base text-center text-gray-200">
        All rights reserved 2021
      </p>
    </footer>
  </div>
</template>

<script>
import PostPreview from '@/components/Items/PostPreview.vue'
import metadata from '@/utils/metadata'

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
  },
  head () {
    return {
      title:"Lucian Cucu | Blog",
      meta: metadata({
        title:"",
        description:"My personal page and blog. You will find many fun and interesting articles about muscic, travel and other cool stuff!",
        image:"https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8d2ViJTIwZGV2ZWxvcG1lbnR8ZW58MHx8MHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
        url:"https://luciancucu.com/",
      })
    }
  }
}

</script>
