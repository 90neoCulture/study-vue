<template>
  <div class="home">
    <FormPage msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import FormPage from "@/components/FormPage.vue";

export default {
  name: "Home",
  components: {
    FormPage
  }
};
</script>
