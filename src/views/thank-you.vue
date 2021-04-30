<template>
  <div class="thank-you">
    <img class="img-background" src="../assets/block1.jpg" alt="" />
    <div class="barcode">
      <img src="../assets/qr-code.png" alt="" />

      <h3 style="margin-top: 10px; font-weight: bold; color: white;">
        <i class="el-icon-loading"></i> Validating Please Wait...
      </h3>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myVar: null,
    };
  },
  mounted() {
    this.testFunction();
  },
  methods: {
    testFunction() {
      let self = this;
      this.myVar = setInterval(function() {
        self.$router.push("/");
        self.myStopFunction()
      }, 9000);
    },
    myStopFunction() {
      clearInterval(this.myVar);
    },
  },
};
</script>

<style lang="scss">
.thank-you {
  position: relative;
  .img-background {
    width: 100%;
    height: 100vh;
    opacity: 0.3;
    object-fit: cover;
  }
  .barcode {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: black;
    padding: 30px;
    img {
      height: 250px;
      width: 250px !important;
      max-width: initial;
      object-fit: cover;
    }
  }
}
</style>
