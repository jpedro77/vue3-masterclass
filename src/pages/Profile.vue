<template>
  <div class="flex-grid">
    <div class="col-3 push-top">

      <user-profile-card :user="user"/>
      <user-profile-card-editor :user="user"/>

      <p class="text-xsmall text-faded text-center">Member since june 2003, last visited 4 hours ago</p>

      <div class="text-center">
        <hr>
        <a href="edit-profile.html" class="btn-green btn-small">Edit Profile</a>
      </div>

    </div>

    <div class="col-7 push-top">

      <div class="profile-header">
        <span class="text-lead">
          Joker's recent activity
        </span>
        <a href="#">See only started threads?</a>
      </div>

      <hr>

      <post-list :posts="user.posts"/>
    </div>
  </div>
</template>

<script>
import PostList from '@/components/PostList'
import UserProfileCard from '@/components/UserProfileCard'
import UserProfileCardEditor from '@/components/UserProfileCardEditor'
import { mapGetters } from 'vuex'

export default {
  name: 'Profile',
  components: {
    PostList,
    UserProfileCard,
    UserProfileCardEditor
  },
  computed: {
    ...mapGetters({ user: 'authUser' })
  }
}
</script>

<style>

</style>
