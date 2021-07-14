<template>
  <div>
    <div
      class="post-thumnail"
      :style="{backgroundImage: 'url(' + thumbnail + ')'}"
    />
    <div class="post-content target=blank">
      <h1 class="text-center text-4xl pt-8">
        {{ title }}
      </h1>
      <div class="border-b border-green-600 mb-8 mx-auto prose lg:prose-xl">
        </div>
      <article class="mx-auto prose lg:prose-xl">
        <div v-html="previewText" />
      </article>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PostPreview',
  props: {
    id: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    previewText: {
      type: String,
      required: true
    },
    thumbnail: {
      type: String,
      required: false
    }
  }
}
</script>
