<template>
  <div>
    <TheHeader/>
    <main>
      <TheCalculator></TheCalculator>
    </main>
  </div>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue'
import TheCalculator from './components/TheCalculator.vue'
export default {
  name: 'App',
  components: {
    TheHeader,
    TheCalculator
  },
  mounted() {
    let testLibrary = document.createElement("script");
    testLibrary.setAttribute(
      "src",
      "https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"
    );
    document.head.appendChild(testLibrary);
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

* {
  box-sizing: border-box;
}

html {
  font-family: "Montserrat", sans-serif;
  padding: 0;
  margin: 0;
}

body {
  margin: 0;
}

main {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 90vh;
}

header {
  display: fixed;
}
</style>
