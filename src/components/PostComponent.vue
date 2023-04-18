<template>
  <h1>PostComponent</h1>
  <div>
    <form @submit="postData" method="post">
      <div>
        <label for="userId">UserID:</label>
        <input type="text" name="userId" v-model="posts.userId" />
      </div>
      <br />
      <br />
      <div>
        <label for="title">Title:</label>
        <input type="text" name="title" v-model="posts.title" />
      </div>
      <br />
      <br />
      <div>
        <label for="body">Body:</label>
        <textarea id="body" rows="6" cols="22" v-model="posts.body"></textarea>
      </div>
      <br />
      <br />
      <button>Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'PostComponent',
  data() {
    return {
      posts: {
        userId: '',
        title: '',
        body: '',
      },
    };
  },
  methods: {
    postData() {
      fetch('https://jsonplaceholder.typicode.com/posts', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          userId: this.userId,
          title: this.title,
          body: this.body,
        }),
      })
        .then((response) => response.json())
        .then((data) => console.log(data));
      // console.warn(this.posts);
      // e.preventDefault();
    },
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
}
,
div {
  margin: 24px auto;
}
,
label {
  font-weight: bolder;
  display: block;
  margin-bottom: 24px;
}
</style>
