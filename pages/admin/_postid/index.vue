<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" @submit="onSubmitted" />
    </section>
  </div>
</template>

<script>
import axios from 'axios'
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
  layout: 'admin',
  components: {
    AdminPostForm
  },
  asyncData(context) {
    return axios
      .get('https://nuxt-learning-692e0.firebaseio.com/post/' + context.params.postid + '.json')
      .then(res => {
        return {
          loadedPost: { ...res.data, id: context.params.postid }
        }
      })
      .catch(e => context.error(e))
  },
  methods: {
    onSubmitted(editedPost) {
      this.$store.dispatch('editPost', editedPost).then(() => {
        this.$router.push('/admin')
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}

@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>
