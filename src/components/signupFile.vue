<template>
  <div class="box box-2">
    <h1>sign up</h1>
    <form action="">
      <label for="username">
        <input
          type="text"
          placeholder="Username*"
          v-model.trim="inputName"
        /><br />
        <div class="error_line" v-if="showError">{{ error }}</div>
        <input
          type="email"
          name="text"
          placeholder="Email*"
          v-model.trim="inputEmail"
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
        <button type="submit" @click.prevent="submitDetails()">sign up</button>
      </label>
    </form>
    <h1 class="signup">sign up</h1>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputName: "",
      inputEmail: "",
      inputPassword: "",
      error: "",
      passError: "",
      showError: false,
    };
  },
  components: {},
  methods: {
    submitDetails() {
      const userName = this.inputName;
      const userPass = this.inputPassword;

      if (this.validate(userName, userPass)) {
        this.inputEmail = "";
        this.inputName = "";
        this.inputPassword = "";
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
<style>
* {
  padding: 0;
  margin: 0;
}

html {
  background-color: rgb(243, 205, 170);
  width: 100%;
  height: 100%;
}
.container {
  background-color: rgb(243, 205, 170);
}
.content {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 100px;
}
img {
  width: 100%;
  height: 400px;
  margin-bottom: 20px;
  border-radius: 10px;
  border-bottom-left-radius: 150px;
  border-bottom-right-radius: 150px;
}
.box {
  background: rgb(32, 13, 1);
  position: relative;
  margin: 30px;
  border-radius: 10px;
  height: 550px;
  width: 300px;
}
span {
  position: absolute;
  color: #fff;
  margin-top: 20px;
  margin-left: 100px;
  font-size: 20px;
  font-weight: bolder;
  cursor: default;
}
a {
  text-decoration: none;
  margin-top: 100px;
  margin-left: 40px;
  color: #fff;
  font-size: 20px;
  font-weight: bold;
  cursor: pointer;
}
a:hover {
  background-color: rgba(255, 255, 255, 0.63);
  color: rgb(32, 13, 1);
}
.box-2 {
  background-color: gray;
}
form {
  margin-top: 100px;
}
input {
  width: 240px;
  height: 30px;
  margin: 10px;
  padding: 5px;
  margin-left: 30px;
  border-radius: 8px;
  font-size: 15px;
  color: rgb(32, 13, 1);
  background: rgb(243, 205, 170);
  border: none;
  outline: none;
}
button {
  width: 240px;
  height: 30px;
  margin: 10px;
  margin-left: 30px;
  border: none;
  font-size: 20px;
  border-radius: 8px;
  color: #fff;
  background-color: rgb(32, 13, 1);
  cursor: pointer;
}

h1 {
  text-align: center;
  color: rgb(32, 13, 1);
  font-weight: bolder;
  text-transform: uppercase;
  padding-top: 0px;
  cursor: default;
}
.signup {
  margin-top: 50px;
}
::-webkit-input-placeholder {
  color: rgba(32, 13, 1, 0.5);
  padding-left: 5px;
  font-weight: bold;
}
::-moz-placeholder {
  color: rgb(32, 13, 1, 0.5);
  padding-left: 5px;
  font-weight: bold;
  opacity: 1;
}
:-ms-input-placeholder {
  color: rgb(32, 13, 1, 0.5);
  padding-left: 5px;
  font-weight: bold;
  opacity: 1px;
}
.error_line {
  padding: 0;
  margin: 0;
  color: red;
  margin-left: 10px;
  font-size: 1rem;
  font-weight: 400;
}
@media screen and (max-width: 576px) {
  * {
    margin: 0;
    padding: 0;
  }
  html {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
  }
  .content {
    display: grid;
    margin: 0;
    padding: 0;
  }
}
</style>
