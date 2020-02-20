<template>
  <div
    class="container"
    :class="{ 'light-background': !isDarkMode, 'dark-background': isDarkMode }"
  >
    <div class="request" :class="{ 'light-request': isDarkMode, 'dark-request': !isDarkMode }">
      Don't have a Design+Code HQ account?
      <router-link to="/request">Request an account</router-link>
    </div>
    <div class="login">
      <img src="@/assets/DCHQ.svg" v-show="isDarkMode" />
      <img src="@/assets/DCHQ-dark.svg" v-show="!isDarkMode" />
      <h4 :class="{ 'light-text': isDarkMode, 'dark-text': !isDarkMode }">Sign into Design+Code HQ</h4>
      <input
        type="email"
        placeholder="Email"
        :class="{ 'light-field': isDarkMode, 'dark-field': !isDarkMode }"
      />
      <input
        type="password"
        placeholder="Password"
        :class="{ 'light-field': isDarkMode, 'dark-field': !isDarkMode }"
      />
      <button>Sign In</button>
      <router-link
        to="/recover"
        :class="{ 'light-link': isDarkMode, 'dark-link': !isDarkMode }"
      >Forgot your password?</router-link>
      <button @click="toggleDarkMode">Toggle</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignIn",
  data() {
    return {
      isDarkMode: true
    };
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      document.body.style.background = this.isDarkMode ? "#212c4f" : "#f0f3f5";
    }
  }
};
</script>


