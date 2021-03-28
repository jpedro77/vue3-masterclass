<template>
  <div class="col-full">
    <div class="forum-list">

      <h2 class="list-title">
        <router-link v-if="categoryId" :to="{name: 'Category', params: {id: categoryId}}">{{ title }}</router-link>
        <span v-else>{{ title }}</span>
      </h2>

      <forum-list-item v-for="forum in forums" :forum="forum" :key="forum.id"/>

    </div>
  </div>
</template>

<script>
import ForumListItem from '@/components/ForumListItem'

export default {
  props: {
    forums: {
      required: true,
      type: Array
    },
    title: {
      type: String,
      default: 'Forums'
    },
    categoryId: {
      required: false,
      type: String
    }
  },
  components: {
    ForumListItem
  }
}
</script>

<style>

</style>
