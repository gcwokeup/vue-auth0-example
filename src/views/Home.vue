<template>
<div class="home">
  <section class="hero is-dark">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">
          Giphy Search       
        </h1>
        <h2 class="subtitle">
          Log in to search for Gifs
        </h2>
        <div class="button-block">
            <button v-if="!$auth.isAuthenticated" @click="login" class="button is-xl is-dark">Sign Up to browse Gifs</button>
            <h3 v-if="$auth.isAuthenticated" class="is-size-3 has-background-dark welcome">Welcome, {{ $auth.user.name }}!</h3>
        </div>
      </div>
    </div>
  </section>
</div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "home",
  methods: {
    // Log the user in
    login() {
      this.$auth.loginWithRedirect();
    }
  }
};
</script>
