<template>
  <div>
    Количество лайков: <strong>{{ likes }}</strong>
  </div>
  <div>
    Количество дислайков: <strong>{{ dislikes }}</strong>
  </div>
  <button @click="addLike">Лайк!</button>
  <button @click="addDislike">Дизлайк!</button>
</template>
<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
    };
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    },
  },
};
</script>
<style></style>
