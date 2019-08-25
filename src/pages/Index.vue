<template>
  <Layout>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image
      alt="Example image"
      src="~/favicon.png"
      width="135"
    />

    <h1>Hello, world!</h1>

    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Pariatur excepturi labore tempore expedita, et iste tenetur suscipit explicabo! Dolores, aperiam non officia eos quod asperiores
    </p>

    <PostList
      v-for="edge in $page.allPost.edges"
      :key="edge.node.id"
      :post="edge.node"
    />

    <p class="home-links">
      <a
        href="https://gridsome.org/docs"
        target="_blank"
        rel="noopener"
      >Gridsome Docs</a>
      <a
        href="https://github.com/gridsome/gridsome"
        target="_blank"
        rel="noopener"
      >GitHub</a>
    </p>

  </Layout>
</template>

<script>
import PostList from "@/components/PostList"
export default {
  components: {
    PostList
  },
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<page-query>
query {
  metaData {
    siteName
    siteDescription
  }
  allPost {
    totalCount
    edges {
      node {
        id
        title
        timeToRead
        description
        date (format: "D MMMM YYYY")
        path
      }
    }

  }
}
</page-query>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
