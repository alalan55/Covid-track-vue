<template>
  <Capa />

  <main>
    <!-- <Sobre /> -->
    <Brasil />
  </main>
  <Footer />
</template>

<script>
import Capa from "./components/Capa";
// import Sobre from './components/Sobre'
import Brasil from "./components/Brasil";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Capa,
    // Sobre,
    Brasil,
    Footer,
  },
};
</script>

<style>

@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;300;400;500;600;800&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "Poppins", sans-serif;
}
</style>
