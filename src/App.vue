<script setup>
import Heroes from "./components/Heroes.vue";
import Footer from "./components/Footer.vue";
import OurTeam from "./components/OurTeam.vue";
import Feature from "./components/Feature.vue";
</script>

<template>
  <Heroes />

  <Feature />

  <OurTeam />

  <Footer />
</template>

<script>
export default {
  data() {
    return {
      post: [],
      isLoading: false,
    };
  },
  methods: {
    getPosts() {
      this.isLoading = true;

      fetch("https://jsonplaceholder.typicode.com/posts/")
        .then((response) => response.json())
        .then((data) => {
          this.post = data;
          this.isLoading = false;
        });
    },
  },
  mounted() {
    this.getPosts();
  },
};
</script>
