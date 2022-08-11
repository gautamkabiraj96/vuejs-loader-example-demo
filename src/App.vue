<template>
  <div id="app">
    <div class="np-content">
      <div v-if="isLoading">
        <Loader />
      </div>
      <div v-else>
        <div class="np-loader-btn">
          <button @click="toggleLoader">Show loader</button>
        </div>
      </div>
    </div>
    <div class="np-credits">wwww.nightprogrammer.com</div>
  </div>
</template>

<script>
import Loader from "./Loader";
export default {
  name: "App",
  data() {
    return {
      isLoading: false,
    };
  },
  components: {
    Loader,
  },
  methods: {
    toggleLoader() {
      this.isLoading = true;
      setTimeout(() => {
        this.isLoading = false;
      }, 2000);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
}

.np-content {
  height: 300px;
  width: 400px;
  background: #eee;
  position: relative;
}

button {
  background-color: #004cbe;
  color: #ffffff;
  border: 0px;
  border-radius: 6px;
  padding: 6px 20px;
  margin-right: 1em;
  cursor: pointer;
  transition: all 0.3s;
}

button:hover {
  background-color: #2f79e7;
  transition: all 0.3s;
}

.np-loader-btn {
  padding: 16px;
}

.np-credits {
  font-size: 12px;
  margin-top: 12px;
  color: #4b4b4b;
}
</style>