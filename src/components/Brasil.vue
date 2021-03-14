<template>
  <div class="conteudo-main">
    <div class="texto-brasil">
      <h1>Como o Brasil se encontra?</h1>
    </div>

    <transition name="fade">
      <div class="cards" v-if="temDados">
        <div class="top">
          <div class="card recuperados">
            <div class="overlay"></div>
            <span
              >recuperados <br />
              {{ data.recovered.toLocaleString() }}
            </span>
          </div>
        </div>
        <div class="middle">
          <div class="card ativos">
            <span
              >ativos <br />
              {{ data.active.toLocaleString() }}</span
            >
          </div>
          <div class="card mortes">
            <span
              >mortes <br />
              {{ data.deaths.toLocaleString() }}</span
            >
          </div>
        </div>
        <div class="bottom">
          <div class="card casosHoje">
            <span
              >casos <br />
              {{ data.cases.toLocaleString() }}</span
            >
          </div>
          <div class="card testados">
            <span>testados <br />{{ data.totalTests.toLocaleString() }}</span>
          </div>
          <div class="card criticos">
            <span
              >criticos <br />
              {{ data.critical.toLocaleString() }}</span
            >
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
      url: "https://coronavirus-19-api.herokuapp.com/countries/brazil",
      data: {},
      options: { method: "GET", mode: "cors", cache: "default" },
      temDados: false,
      recovered: Number,
      active: Number,
      deaths: Number,
      cases: Number,
      totalTests: Number,
    };
  },
  mounted() {
  //  this.getInfo();
   // this.toLocal();
    this.getGlobalInfo();
  },
  methods: {
    getInfo() {
      axios.get(this.url).then((res) => {
        if (res.status == 200) {
          // this.temDados = true;
          // this.data = res.data;
          // this.recovered = res.data.recovered;
          // this.active = res.data.active;
          // this.deaths = res.data.deaths;
          // this.cases = res.data.cases;
          // this.totalTests = res.data.totalTests;
          // this.critical = res.data.critical;

        //  console.log(res.data.recovered);
        }
        //  this.toLocal(res.data);
      });
    },
     getGlobalInfo(){

      fetch(this.url, { methods: "GET", mode: "cors" }).then((res) =>{
          if(res.ok)
          {
            res.json()
            .then(dados =>{
              this.data = dados;
              this.temDados = true;
            })
          }
      })
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
.conteudo-main {
  padding: 2%;
  background-color: black;
}

.conteudo-main .texto-brasil {
  text-align: center;
  color: white;
}

.conteudo-main .texto-brasil h1 {
  font-weight: 400;
}

.conteudo-main .cards {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
}

.conteudo-main .cards .top {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.conteudo-main .cards .top > div {
  /* background-color: #fffafa; */
  border: 1px solid #fffafa;
  font-size: 1.5rem;
  text-align: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  border-radius: 15px;
  padding: 7%;
  width: 100%;
  margin: 10px;
  -webkit-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
  -webkit-box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
  box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
}
.top > div span {
  color: white;
  /* bottom:0;
    opacity: 0; */
  /* transition: 1s; */
}
.top > div:hover {
  background: #fffafa;
  transition: 0.4s ease-in-out;
}
.top > div:hover span {
  color: black;
  opacity: 1;
}
.card:hover .overlay {
  opacity: 1;
}

.conteudo-main .cards .middle {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}

.conteudo-main .cards .middle > div {
  /* background-color: #fffafa; */
  border: 1px solid #fffafa;
  font-size: 1.5rem;
  text-align: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  border-radius: 15px;
  padding: 7%;
  width: 100%;
  margin: 10px;
  -webkit-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
  -webkit-box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
  box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
}
.middle > div span {
  color: white;
}
.middle > div:hover {
  background: #fffafa;
  transition: 0.4s ease-in-out;
}
.middle > div:hover span {
  color: black;
}

.conteudo-main .cards .bottom {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
}

.conteudo-main .cards .bottom > div {
  /* background-color: #fffafa; */
  border: 1px solid #fffafa;
  font-size: 1.5rem;
  text-align: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  -webkit-transition: 0.2s ease-in-out;
  transition: 0.2s ease-in-out;
  border-radius: 15px;
  padding: 7%;
  width: 100%;
  margin: 10px;
  transition: 0.2s ease-in-out;
  -webkit-box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
  box-shadow: -1px 4px 18px -8px rgba(0, 0, 0, 0.75);
}
.bottom > div span {
  color: white;
}
.bottom > div:hover {
  background: #fffafa;
  transition: 0.4s ease-in-out;
}
.bottom > div:hover span {
  color: black;
}

.conteudo-main .cards > div {
  margin: 10px;
}

@media screen and (max-width: 850px) {
  .bottom {
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
  }
}

@media screen and (max-width: 655px) {
  .top > div {
    font-size: 1rem !important;
  }
  .middle > div {
    font-size: 1rem !important;
  }
  .bottom > div {
    font-size: 1rem !important;
  }
}

@media screen and (max-width: 440px) {
  .top > div {
    font-size: 0.8rem !important;
  }
  .middle > div {
    font-size: 0.8rem !important;
  }
  .bottom > div {
    font-size: 0.8rem !important;
  }
}
</style>