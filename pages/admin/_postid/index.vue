<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" />
    </section>
  </div>
</template>

<script>
  import AdminPostForm from '@/components/Admin/AdminPostForm'

  export default {
    layout: 'admin',
    components: {
      AdminPostForm
    },
    data() {
      return {
        loadedPost: {
          author: 'Takahisa',
          title: 'my post',
          content: 'hoge hoge hoge',
          thumbnailLink: 'https://www.photolibrary.jp/mhd3/img547/450-20171015133637110801.jpg',
        }
      }
    },
    methods: {
      onSave() {
        console.log(this.editedPost)
      },
      onCancel() {
        this.$router.push('/admin')
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