<template>
  <div class="forum-listing">
    <div class="forum-details">
      <router-link class="text-xlarge" :to="{ name: 'Forum', params: { id: forum.id } }">{{ forum.name }}</router-link>
      <p>{{ forum.description }}</p>
    </div>

    <div class="threads-count">
      <p>
        <span class="count">{{ forum.threads?.length }}</span>
        {{ forumThreadsWord(forum) }}
      </p>
    </div>

    <div class="last-thread"></div>
  </div>
</template>

<script>
export default {
  props: {
    forum: {
      required: true,
      type: Object
    }
  },
  methods: {
    forumThreadsWord (forum) {
      if (forum.threads?.length) {
        return forum.threads.length > 1 ? 'Threads' : 'Thread'
      } else {
        return 'no threads'
      }
    }
  }
}
</script>

<style>

</style>
