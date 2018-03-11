<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">{{ loadedPost.title }}</h1>
      <div class="post-details">
        <div class="post-detail">Last Updated On: {{ loadedPost.updatedDate }}</div>
        <div class="post-detail">Written By: {{ loadedPost.author }}</div>
      </div>
      <p class="post-content">{{ loadedPost.content }}</p>
    </section>
    <section class="post-feedback">
      <p>Let me know what you think about this post. Send a mail to: <a href="mailto:example@example.com">My Email </a></p>
    </section>
  </div>
</template>

<script>
export default {
  asyncData(context, cb) {
    setTimeout(() => {
      cb(null, {
        loadedPost: {
          id: "1",
          title: "First Post (ID: " + context.params.id + ")",
          previewText: "This is our first post!",
          author: "Joshua",
          updatedDate: new Date(),
          content: "Dummy test wawawawawa",
          thumbnailLink: "http://www.placecage.com/gif/200/300"
        }
      });
    }, 1000);
  }
};
</script>

<style scoped>
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
