<template>
  <div class="hero">
    <header>
      <h1>Covid-19</h1>
      <span>Dados Gerais sobre a Covid</span>
    </header>

    <transition name="fade">
      <div class="conteudo-global" v-if="temDados">
        <div class="content">
          <div class="casos-global cont">
            <h1>{{ data.cases.toLocaleString() }}</h1>
            <span>casos</span>
          </div>

          <div class="barr"></div>

          <div class="fatalidades-global cont">
            <h1>{{ data.deaths.toLocaleString() }}</h1>
            <span>mortes</span>
          </div>

          <div class="barr"></div>

          <div class="recuperados-global cont">
            <h1>{{ data.recovered.toLocaleString() }}</h1>
            <span>recuperados</span>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
const axios = require("axios");

export default {
  data() {
    return {
      url: "https://coronavirus-19-api.herokuapp.com/countries/world",
      data: {},
      temDados: false,
      cases: Number,
      deaths: Number,
    };
  },
  mounted() {
    // this.getInfoGlobal();
    this.getGlobalInfo();
  },
  methods: {
    getInfoGlobal() {
      axios.get(this.url).then((res) => {
        if (res.status == 200) {
          // this.temDados = true;
          // this.data = res.data;
          // this.cases = res.data.cases;
          // this.deaths = res.data.deaths;
          // this.recovered = res.data.recovered;
        }
      });
    },

    getGlobalInfo() {
      fetch(this.url, { methods: "GET", mode: "cors" }).then((res) => {
        if (res.ok) {
          res.json().then((dados) => {
            this.data = dados;
            this.temDados = true;
          });
        }
      });
    },
  },
};
</script>

<style lang="css" scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.hero {
  height: 100vh;
  background-color: black;
  /* background: url(https://images.pexels.com/photos/1526/dark-blur-blurred-gradient.jpg?auto=compress&cs=tinysrgb&h=750&w=1260) no-repeat; */
  background: url(https://images.pexels.com/photos/1040499/pexels-photo-1040499.jpeg?auto=compress&cs=tinysrgb&h=750&w=1260)
    no-repeat;
  background-size: cover;
  filter: grayscale(100%);
}

.hero header {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  height: 150px;
  -webkit-animation: header-load 500ms ease-in;
  animation: header-load 500ms ease-in;
}

.hero header h1 {
  margin-top: 25px;
  font-size: 2.9rem;
  color: white;
}

.hero header span {
  margin-top: 25px;
  font-size: 2rem;
  color: white;
}

.hero .conteudo-global {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  height: calc(100vh - 150px);
  -webkit-animation: header-load 500ms ease-in;
  animation: header-load 500ms ease-in;
}

.hero .conteudo-global .content {
  border-top: 1px solid white;
  -ms-flex-item-align: end;
  align-self: flex-end;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  margin: 0 auto;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  padding: 1%;
  height: 200px;
}

.hero .conteudo-global .content .bar {
  border: 4px white;
  width: 40px;
  color: white;
}

.hero .conteudo-global .content .barr {
  border: 0.1px solid white;
  margin: 0 5%;
  height: 85%;
}

.hero .conteudo-global .content .cont {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
}

.hero .conteudo-global .content .cont h1 {
  font-size: 3.5rem;
  color: white;
  -webkit-transition: 0.1s ease-in-out;
  transition: 0.1s ease-in-out;
}

.hero .conteudo-global .content .cont span {
  color: white;
  -webkit-transition: 0.1s ease-in-out;
  transition: 0.1s ease-in-out;
}

@media screen and (max-width: 996px) {
  .cont h1 {
    font-size: 3rem !important;
  }
}

@media screen and (max-width: 868px) {
  .content {
    -webkit-box-pack: justify;
    -ms-flex-pack: justify;
    justify-content: space-between;
  }
  .barr {
    display: none !important;
  }
  .cont {
    margin: 0 15px;
  }
  .cont h1 {
    font-size: 2.4rem !important;
  }
}

@media screen and (max-width: 665px) {
  header {
    padding: 1%;
    text-align: center;
  }
  .cont {
    margin: 0 15px;
  }
  .cont h1 {
    font-size: 1.5rem !important;
  }
}

@media screen and (max-width: 440px) {
  header {
    padding-top: 25% !important;
  }
  .cont {
    margin: 0 15px;
  }
  .cont h1 {
    font-size: 0.75rem !important;
  }
  .cont span {
    font-size: 0.6rem !important;
  }
}

@-webkit-keyframes header-load {
  0% {
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
}

@keyframes header-load {
  0% {
    -webkit-transform: translateY(-100%);
    transform: translateY(-100%);
  }
  100% {
    -webkit-transform: translateY(0);
    transform: translateY(0);
  }
}
</style>