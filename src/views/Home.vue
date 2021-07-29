<template>
  <div>
    <Header />
    <home />
  </div>
</template>

<script>
import home from "../components/Home";
import Header from "../components/Header";
export default {
  name: "Home",
  components: {
    home,
    Header,
  },
};
</script>
