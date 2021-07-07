<template>
  <div class="blog-page">
    <section class="intro">
      <h1>Blog about music</h1>
    </section>
    <section class="featured-posts">
      <PostPreview
        id="1"
        thumbnail="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8bmF0dXJlfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"
        title="Ciao"
        preview-text="This is my first post!"
      />
      <PostPreview
        id="2"
        thumbnail="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8bmF0dXJlfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"
        title="Ciao"
        preview-text="This is my second post!"
      />
      <PostPreview
        id="3"
        thumbnail="https://images.unsplash.com/photo-1470071459604-3b5ec3a7fe05?ixid=MnwxMjA3fDB8MHxzZWFyY2h8M3x8bmF0dXJlfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=60"
        title="Ciao"
        preview-text="This is my third post!"
      />
    </section>
  </div>
</template>

<script>
import PostPreview from '@/components/Items/PostPreview'

export default {
  components: {
    PostPreview
  }
}
</script>
