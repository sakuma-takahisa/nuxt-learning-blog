<template>
  <div class="single-post-page">
    <section class="post">
      <h1>{{ loadedPost.title }}</h1>
      <div class="post-details">
        <div>Last updateed : {{ loadedPost.updatedDate }}</div>
        <div>written by : {{ loadedPost.author }}</div>
      </div>
      <p>{{ loadedPost.content }}</p>
    </section>
    <section class="post-feedback">
      <p>Let me know what you think about this post</p>
    </section>

  </div>
</template>

<script>
  export default {
    asyncData(context, callback) {
      setTimeout(() => {
        callback(null, {
          loadedPost: {
            id: '1',
            title: "First Post (ID: " + context.route.params.id +  " )",
            previewText: 'This is post',
            author: 'Takahisa',
            updatedDate: new Date(),
            content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem, optio temporibus laudantium reiciendis ipsum cumque quos placeat ratione maiores id cum! Consequatur quo, assumenda commodi quia temporibus soluta dignissimos minus?',
            thumbnail: 'https://www.photolibrary.jp/mhd3/img547/450-20171015133637110801.jpg',
          }
        })
      },1000)
    },
  }
</script>

<style lang="scss" scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>