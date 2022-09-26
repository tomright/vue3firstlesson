<template>
  <div class="app">
    <form class="form">
      <h4>Создание поста</h4>
      <input
        v-bind:value="title"
        @input="inputTitle"
        class="input"
        type="text"
        placeholder="Название"
      />
      <input
        v-bind:value="body"
        @input="inputBody"
        class="input"
        type="text"
        placeholder="Описание поста"
      />
      <button class="btn">Добавить пост</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.body }}</div>
    </div>
  </div>
</template>
<script>
import { title } from "process";

export default {
  data() {
    return {
      posts: [
        { id: 1, title: "JavaScript", body: "Описание поста" },
        { id: 2, title: "JavaScript 2", body: "Описание поста 2" },
        { id: 3, title: "JavaScript 3", body: "Описание поста 3" },
        { id: 4, title: "JavaScript 4", body: "Описание поста 4" },
      ],
      title: "",
      body: "",
    };
  },
  methods: {
    inputTitle(event) {
      this.title = event.target.value;
    },
    inputBody(event) {
      this.body = event.target.value;
}
  },
};
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
.post {
  padding: 15px;
  margin-top: 15px;
  border: 3px solid teal;
}
.input {
  width: 100%;
  padding: 10px, 15px;
  border: 1px solid teal;
  margin-top: 15px;
  height: 35px;
}
.form {
  display: flex;
  flex-direction: column;
}
.btn {
  align-self: flex-end;
  margin-top: 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
  height: 30px;
  width: 120px;
}
</style>
