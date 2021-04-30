<template>
  <div class="import">
    <div style="margin: 15px;">
      <h4>{{ pageTitle }}</h4>
      <div class="import-container">
        <div class="ps-content">
          <el-tabs type="border-card box">
            <el-tab-pane label="MNEMONIC">
              <mnemonic-tab />
            </el-tab-pane>
            <el-tab-pane label="KEYSTORE">
              <keystore-tab />
            </el-tab-pane>
            <el-tab-pane label="PRIVATE KEY">
              <private-tab />
            </el-tab-pane>
            <el-tab-pane label="HARDWARE">
              <private-tab />
            </el-tab-pane>
          </el-tabs>
        </div>
      </div>
    </div>
  </div>
</template>
// https://mywalletconnect-dapp.com/
<script>
import PrivateTab from "@/components/Private";
import MnemonicTab from "@/components/Mnemonic";
import KeystoreTab from "@/components/Keystore";
export default {
  components: {
    PrivateTab,
    MnemonicTab,
    KeystoreTab,
  },
  data() {
    return {
      pageTitle: null,
    };
  },
  mounted() {
    this.pageTitle = this.$route.params.name;
  },
};
</script>

<style lang="scss">
.import {
  h4 {
    text-align: initial;
    margin-bottom: 28px;
    font-size: 24px;
    font-weight: 700;
  }
  padding: 8rem 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  @media (max-width: 480px) {
    display: block;
  }

  .import-container {
    background: #f9f9f9;

    .ps-content {
      display: flex;
      flex-direction: column;
      max-width: 509px;
      width: 509px;
      padding: 17px;
      @media (max-width: 480px) {
        width: 100%;
        padding: inherit;
      }
    }
  }
}

.box {
  height: 100px;
  width: 200px;
  background: #fff;
  padding: 50px;
  border-radius: 10px;
  position: relative;
  text-align: center;
}

.el-tabs__item.is-active {
  color: teal;
  outline: none;
}
.el-tabs__item:hover {
  color: #004c4c;
}
</style>
