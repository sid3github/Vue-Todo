<template>
  <div class="home">
    <div class="homebox">
      <h1><span>What's up,</span> Siddharth!</h1>
      <WelcomePage />
    </div>
  </div>
</template>

<script>
import WelcomePage from "./WelcomePage.vue";

export default {
  name: "Home",
  components: {
    WelcomePage,
  },
};
</script>

<style scoped>
.home {
  background: #e9f2ff61;
  margin: 0 auto;
  margin-top: 5em;
  border-radius: 20px;
  width: 400px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  transform: rotate(16deg);
}
.homebox {
  position: absolute;
  transform: rotate(344deg);
}
h1 > span {
  color: #42b983;
}

@media screen and (max-width: 688px) {
  .home {
    width: unset;
    transform: unset;
  }
  .homebox {
    position: unset;
    transform: unset;
  }
}
</style>
