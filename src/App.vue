<template>
  <div class="container">
    <div class="content">
      <div class="box box-1">
        <span>NFT LOGIN</span>
        <img src="./assets/Nft-image.jpg" alt="NFT" />
        <a @click="this.activeComp = 'comp-signup'">
          <strong>SIGN UP</strong></a
        >
        <a @click="this.activeComp = 'comp-login'"> <strong>SIGN IN</strong></a>
      </div>

      <component :is="activeComp"></component>
    </div>
  </div>
</template>

<script>
import compSignup from "./components/signupFile.vue";
import compLogin from "./components/loginFile.vue";

export default {
  data() {
    return {
      activeComp: "",
    };
  },
  components: {
    compSignup,
    compLogin,
  },
};
</script>
<style></style>
