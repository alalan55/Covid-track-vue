<template>
  <div class="container">
    <div class="conteudo">
      <div class="lado-esquerdo">
          <div class="img">
              <img src="../assets/icons/Coronavirus-Flat/PNG/512/doctor.png" alt="">
          </div>
      </div>
      <div class="lado-direito">

        <div class="textos">
          <h1> Sobre <br>   COVID-19</h1>
          <p>
            A doença do coronavírus (COVID-19) é uma doença infecciosa causada
            por um coronavírus recém-descoberto. A maioria das pessoas que
            adoece em decorrência da COVID-19 apresentará sintomas leves a
            moderados e se recuperará sem tratamento especial. O vírus que causa
            a COVID-19 é transmitido principalmente por meio de gotículas
            geradas quando uma pessoa infectada tosse, espirra ou exala. Essas
            gotículas são muito pesadas para permanecerem no ar e são
            rapidamente depositadas em pisos ou superfícies.
          </p>
          <div class="textos-bottom">
              <div class="esquerdo">
                  <ul>
                      <li><i class="fas fa-check-circle"></i> Lave suas mãos</li>
                       <li><i class="fas fa-check-circle"></i> Use máscara</li>
                        <li><i class="fas fa-check-circle"></i> Beba água</li>
                  </ul>
              </div>
              <div class="direito">
                   <ul>
                      <li><i class="fas fa-times-circle"></i> Evite contato muito próximo</li>
                      <li><i class="fas fa-times-circle"></i> Mantenha distância social</li>
                      <li><i class="fas fa-times-circle"></i> Não toque seu rosto</li>
                  </ul>
              </div>
          </div>
        </div>
      </div>
    </div>


  </div>
</template>

<script>
export default {};
</script>

<style lang="css" scoped>
.container {
  height: 100vh;
}
.conteudo {
    height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  /* border: 1px solid; */
  max-width: 1300px;
  margin: 0 auto;
  /* flex-wrap: wrap; */
  padding: 1%;
 
}
.conteudo>div{
     /* align-self: flex-end; */
}

.lado-esquerdo{
 width: 100%;
 transition: .2s ease-in-out;
}
.lado-direito{
 width: 100%;
 transition: .2s ease-in-out;
}

.textos-bottom{
    display: flex;
    
}
.textos-bottom>div{
    /* border: 1px solid; */
    width: 100%;
    margin-top: 25px;
    
}
.textos-bottom .direito ul{
    list-style: none;
}
.textos-bottom .direito ul li{
    padding: 2.5%;
}
.textos-bottom .direito ul li i{
   color: #2855eb;
}
.textos-bottom .esquerdo ul{
    list-style: none;
}
.textos-bottom .esquerdo ul li{
      padding: 2.5%;
      
}
.textos-bottom .esquerdo ul li i{
     color: #f99498;
     
}
.textos{
    max-width: 550px;
}
.textos h1{
   padding-bottom: 5%;
   transition: .2s ease-in-out;
}
.textos p{
   letter-spacing: .06rem;
   text-align: justify;
   transition: .2s ease-in-out;
}
.img{
  width: 100%;
  /* border: 1px solid; */
}
.img img{
  
  object-fit: cover;
}

@media screen and (max-width: 900px){
  .lado-esquerdo{
    display: none;
  }
  .lado-direito{
    /* border: 1px solid; */
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .textos h1{
    text-align: center;
    
  }
}
</style>