<template>
  <div class="col-full">

    <div class="thread-list">

      <h2 class="list-title">Threads</h2>

      <thread-list-item v-for="thread in threads" :key="thread.id" :thread="thread"/>

    </div>

  </div>
</template>

<script>
import ThreadListItem from '@/components/ThreadListItem'

export default {
  props: {
    threads: {
      required: true,
      type: Array
    }
  },
  components: {
    ThreadListItem
  }
}
</script>

<style>

</style>
