<template>
  <div class="app">
   <post-form :posts="posts"/>
   <post-list :posts="posts"/>
  </div>

</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "./components/PostList.vue";
export default {
  components: {
    PostForm, PostList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript', body: 'Описание'},
        {id: 2, title: 'JavaScript 2', body: 'Описание 2'},
        {id: 3, title: 'JavaScript 3', body: 'Описание 3'}
      ],
      title: '',
      body: ''
    }
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      }
      this.posts.push(newPost);
      this.title = '';
      this.body = '';

    },
  } 
}
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


</style>