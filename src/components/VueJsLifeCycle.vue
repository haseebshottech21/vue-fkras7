<template>
  <div>
    <h1>Life Cycle hook in Vue Js</h1>
    <div v-if="display">
      <h1 id="demo">{{ name }}</h1>
    </div>
    <button v-on:click="toggle">Toggle</button>
  </div>
</template>

<script>
export default {
  name: 'VueJsLifeCycle',
  methods: {
    toggle() {
      this.display = !this.display;
    },
  },
  data() {
    return {
      name: 'Rizwan',
      display: true,
    };
  },

  beforeCreate() {
    console.warn('before create', this.name);
  },
  created() {
    // this.name = 'Babar';
    console.warn('create', this.name);
  },
  beforeMount() {
    console.warn('before mount', this.$el);
  },
  mounted() {
    console.warn('mounted', this.$el);
  },
  beforeDestroy() {
    console.warn('beforeDestroyed method called');
  },
  destroyed() {
    console.warn('destroyed method called');
  },
};
</script>
