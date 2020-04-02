<template>
  <section class="post-list">
    <PostPreview
      id="1"
      :is-admin="isAdmin"
      thumbnail="https://www.photolibrary.jp/mhd3/img547/450-20171015133637110801.jpg"
      title="Hello there"
      previewText="this is post"/>
    <PostPreview
      id="2"
      :is-admin="isAdmin"
      thumbnail="https://www.photolibrary.jp/mhd3/img547/450-20171015133637110801.jpg"
      title="Hello hoge"
      previewText="this is post"/>
    <PostPreview
      id="3"
      :is-admin="isAdmin"
      thumbnail="https://www.photolibrary.jp/mhd3/img547/450-20171015133637110801.jpg"
      title="fooooo"
      previewText="this is post"/>
  </section>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview'
export default {
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

</style>