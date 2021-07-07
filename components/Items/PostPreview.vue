<template>
  <div>
    <nuxt-link :to="'/items' + id" class="post-preview">
      <post>
        <div
          class="post-thumnail"
          :style="{backgroundImage: 'url(' + thumbnail + ')'}"
        />
        <div class="post-content">
          <h1>{{ title }}</h1>
          <p>{{ previewText }}</p>
        </div>
      </post>
    </nuxt-link>
  </div>
  </post>
  </nuxt-link>
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
      required: true
    }
  }
}
</script>

<style scoped>

.post-preview {
  border: 1px solid #ccc;
  box-shadow: - 2px 2 px #ccc;
  background-color: white;
  width: 90%;
}

a {
    text-decoration: none;
    color: black;
}

.post-content {
    padding: 10px;
    text-align: center;
}

a:hover .post-content,
a:active .post-content {
    background-color: #ccc;
}

.featured-posts {
    display: flex;
    padding: 20px;
    box-sizing: border-box;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
}

@media (min-width: 850px) {
    .post-preview {
        width: 400px;
        margin: 10px;
    }
}

.post-thumbnail {
    width: 100%;
    height: 200px;
    background-position: center;
    background-size: cover;
}

</style>
