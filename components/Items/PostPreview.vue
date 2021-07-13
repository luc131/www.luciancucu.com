<template>
  <div>
    <div
      class="post-thumnail"
      :style="{backgroundImage: 'url(' + thumbnail + ')'}"
    />
    <div class="post-content target=blank">
      <h1 class="text-center text-5xl">
        {{ title }}
      </h1>
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
