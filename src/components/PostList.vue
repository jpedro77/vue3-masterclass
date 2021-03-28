<template>
  <div class="post-list">

    <post-list-item v-for="post in posts" :post="post" :key="post.id"/>

  </div>
</template>

<script>
import PostListItem from '@/components/PostListItem'

export default {
  props: {
    posts: {
      required: true,
      type: Array
    }
  },
  components: {
    PostListItem
  }
}
</script>

<style>

</style>
