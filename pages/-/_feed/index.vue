<template>
  <div class="post-page">
    <section class="post-list">
      <PostPreview
        v-for="post in posts"
        :id="post.id"
        :key="post.id"
        :title="post.title"
        :preview-text="post.previewText"
      />
    </section>
  </div>
</template>
