<template>
  <div class="col-full">

    <form @submit.prevent="save">
      <div class="form-group">
        <textarea v-model="text" id="" cols="30" rows="10" class="form-input"/>
      </div>
      <div class="form-actions">
        <button class="btn-blue">Submit post</button>
      </div>
    </form>

  </div>
</template>

<script>
export default {
  data () {
    return {
      text: ''
    }
  },
  methods: {
    save () {
      const post = {
        text: this.text,
        publishedAt: Math.floor(Date.now() / 1000),
        userId: 'VXjpr2WHa8Ux4Bnggym8QFLdv5C3'
      }
      this.$emit('save', { post })

      this.text = ''
    }
  }
}
</script>

<style>

</style>
