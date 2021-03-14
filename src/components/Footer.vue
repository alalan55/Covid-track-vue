<template>
    <footer>
        <div class="content-footer">
            <span>Desenvolvido por <a href="https://github.com/alalan55"> Alan Ferreira</a> <i class="fas fa-heart"></i></span>
        </div>
       
    </footer>
</template>
<script>
export default {
    
}
</script>
<style>

.fas{
  color: red;
}

footer {
  padding: 10px;
  background: #333333;
}

footer .content-footer {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  max-width: 1200px;
  margin: 0 auto;
  color: white;
}

footer .content-footer span a {
  text-decoration: none;
  color:rgb(196, 193, 193);
}

</style>