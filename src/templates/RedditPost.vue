<template>
  <Layout>
    <h1>{{ $page.redditPost.title }}</h1>
    <img :src="$page.redditPost.fields.img" :alt="$page.redditPost.title" />
  </Layout>
</template>

<page-query>
  query RedditPost ($path: String!) {
    redditPost(path: $path) {
      title
      path
      fields {
        img
      }
    }
  }
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.redditPost.title,
    };
  },
};
</script>
