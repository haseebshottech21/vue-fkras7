<template>
  <h1>EmployeeList</h1>
  <div v-for="p in post" :key="p.id">
    <h2>{{ p.id }} - {{ p.title }}</h2>
    <p>{{ p.body }}</p>
  </div>
</template>

<script>
import * as Vue from 'vue'; // in Vue 3
import axios from 'axios';
import VueAxios from 'vue-axios';

Vue.use(VueAxios, axios);

export default {
  name: 'EmployeeList',
  data() {
    return {
      post: undefined,
    };
  },
  methods: {
    getData() {
      fetch('https://jsonplaceholder.typicode.com/posts')
        .then((response) => response.json())
        .then((data) => (this.post = data));
    },
  },
  mounted() {
    // console.warn('call');
    this.getData();
  },
};
</script>
