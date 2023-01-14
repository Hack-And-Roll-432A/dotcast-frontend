<template>
  <div class="home">
    <p class="header">dotCast</p>
    <p class="subheader">Listen to Podcast Right on The Dot</p>

    <div class="container">
      <button class="sso">
        <router-link to="/home">
          <p>Sign in with Spotify</p>
        </router-link>
      </button>

      <hr width="60%" size="1" align="center" />

      <button class="guest">
        <router-link to="/home">
          <p class="guest-text">Continue as Guest</p>
        </router-link>
      </button>
    </div>

    <router-view />
  </div>
</template>

<script>
export default {
  name: "LoginView",
  components: {},
};
</script>

<style>
.header {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 700;
  font-size: 5rem;

  color: #00ff57;
}

.subheader {
  font-family: "Poppins";
  font-style: normal;
  font-weight: 400;
  font-size: 1.5rem;
  margin-top: -2.5vh;
  color: #9e9e9e;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 25vh;
}

.sso {
  border-radius: 40px;
  width: 342px;
  height: 68px;
  font-size: 1rem;
  font-weight: 700;
  background: #00ff57;
}

.guest {
  border-radius: 40px;
  width: 342px;
  height: 68px;
  font-size: 1rem;
  font-weight: 700;
}

.guest {
  background: #1e1e1e;
  border-color: white;
}

.guest-text {
  color: white;
}

p {
  color: #171717;
}

hr {
  color: #1e1e1e;
}
</style>
