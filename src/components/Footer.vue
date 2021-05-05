<template>
  <div class="footer">
    <div class="footer-left">
      <nav>
        <ul>
          <li>
            <a href="">Copyright @2020 Wallet Dapps</a>
          </li>
          <li>
            <a href="">Contact Us</a>
          </li>
          <li>
            <a href="">FAQ</a>
          </li>
        </ul>
      </nav>
    </div>
    <div class="header-right"></div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.footer {
  .footer-left {
    display: flex;
    height: 54px;
    padding: 0px 20px;
    background: teal;
    align-items: center;
  }
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: white;
  font-weight: 800;
}
</style>
