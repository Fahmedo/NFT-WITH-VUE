<template>
  <div class="box box-2">
    <h1>login</h1>
    <form action="">
      <label for="username">
        <input
          type="text email"
          placeholder="Username* or Email"
          v-model.trim="inputName"
        /><br />
        <div class="error_line" v-if="showError">{{ error }}</div>
        <input
          type="password"
          name="text"
          placeholder="Password*"
          v-model.trim="inputPassword"
        /><br />
        <div class="error_line" v-if="showError">
          {{ error }} {{ passError }}
        </div>
        <button type="submit" @click.prevent="submitDetail()">login</button>
      </label>
    </form>
    <h1 class="signup">login</h1>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputName: "",
      inputPassword: "",
      passError: "",
      error: "",
      showError: false,
    };
  },
  components: {},
  methods: {
    submitDetail() {
      const userId = this.inputName;
      if (this.validate(userId)) {
        this.inputName = "";
        this.inputPassword = "";
        this.passError = "";
        this.showError = false;
      } else {
        this.showError = true;
      }
    },
    validate(value) {
      const userPass = this.inputPassword;
      this.error = "";
      this.passError = "";
      if (value === "") {
        this.error = "Fill the details";
        return false;
      }
      if (userPass.length < 8) {
        this.passError = "Password is less than 8 characters";
        return false;
      }
    },
  },
};
</script>
<style scoped></style>
