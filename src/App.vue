<template>
  <div id="app">
    <Header />
    <router-view />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";

import Footer from "@/components/Footer.vue";

export default {
  name: "Home",
  components: {
    Header,
    Footer
  }
};
</script>

<style lang="scss">

.private {
  min-height: 435px;

  label {
    color: #565656;
  }
  p {
    color: #006666;
  }
  input {
    background: #eee;
    color: teal !important;
    border: 1px solid teal !important;
    height: 50px;
    background: black;
  }
  button {
    height: 50px;
    background: #004c4c;
    border-radius: 4px;
    transition: all 0.2s ease-in-out;
    span {
      text-transform: uppercase;
      color: white;
      font-size: 20px;
      font-weight: 600;
    }

    &:hover,
    &:active {
      color: white;
      outline: none;
      border-color: #3b99fc;
      background-color: black;
    }
  }

  .el-textarea {
    textarea {
      outline: none !important;
      background: white;
      color: teal !important;
      border: 1px solid teal !important;
      font-weight: 500;
      padding: 12px;
      font-size: 16px;
      resize: none;
      border-radius: 4px;
    }
  }
}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  height: 100%;
  overflow: auto;
  // background-color: black;
}

.blue-home {
  color: #3b99fc;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
