<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost"/>
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm';
export default {
  layout: 'admin',
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPost: {
        author: 'Joshua',
        title: 'First Post!',
        content: 'omg omg omg',
        thumbnailLink: 'http://www.placecage.com/gif/200/300'
      }
    }
  }
}
</script>

<style scoped>
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

