<template>
  <div class="app">
    <Header />
    <Content />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Content from "@/components/Content";

export default {
  name: 'App',

  components: {
    Header,
    Content,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=Roboto+Condensed');
body {
    background: #EFEFEF;
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-style: normal;
    min-width: 480px;
}
</style>