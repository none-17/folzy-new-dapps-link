<template>
  <div class="header">
    <div class="header-left">
      <a class="flex items-end" href="/">
        <img
          class="logo-image w-1/12"
          src="../assets/styles/save-money.png"
          alt="wallet-logo"
        />
        <h2 class="font-semibold text-3xl blue-home">
          Wallet <span style="font-weight: 300; color: teal;">Dapps</span>
        </h2>
      </a>
    </div>
    <div class="header-right">
      <nav>
        <ul>
          <li>
            <a href="">Home</a>
          </li>
          <li>
            <a href="">Connect Dapps</a>
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
.header {
  height: 80px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  box-shadow: 0px 4px 17px -7px rgba(0, 0, 0, 0.77);
  position: fixed;
  width: 100%;
  background: white;
  z-index: 4000;

  .header-left {
    .blue-home {
      font-weight: 800;
      font-size: 25px;
      color: black;
      margin-left: 14px;
    }
  }

  .header-right {
    @media (max-width: 480px) {
      display: none;
    }
    li {
      margin: 0 20px;
      a {
        font-weight: 800;
        font-size: 18px;
        color: #004c4c;
        transition: all 0.5s;
        &:hover {
          color: #b2d8d8;
        }
      }
    }
  }
  .logo-image {
    width: 50px;
    height: 50px;
    object-fit: contain;
  }
}
h3 {
  margin: 40px 0 0;
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
  color: #42b983;
}
</style>
