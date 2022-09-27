<template>
  <div v-if="posts.length>0">
    <h3>Список постов:</h3>
    <post-item
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
      v-for="post in posts"
    />
  </div>
  <h2 v-else style="color: red">Список постов пуст</h2>
</template>
<script>
import PostItem from "@/components/PostItem.vue";
export default {
  components: { PostItem },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style scoped>
.post {
  padding: 15px;
  margin-top: 15px;
  border: 3px solid teal;
}
</style>
