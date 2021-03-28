<template>
  <div class="col-full push-top">
    <h1>{{ category.name }}</h1>
  </div>

  <forum-list
    :forums="getForumsForCategory(category)"
    :title="category.name"
  />

</template>

<script>
import ForumList from '@/components/ForumList'

export default {
  props: {
    id: {
      required: true,
      type: String
    }
  },
  components: {
    ForumList
  },
  computed: {
    category () {
      return this.$store.state.categories.find(category => category.id === this.id)
    }
  },
  methods: {
    getForumsForCategory (category) {
      return this.$store.state.forums.filter(forum => forum.categoryId === category.id)
    }
  }
}
</script>

<style>

</style>
