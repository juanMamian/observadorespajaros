<template>
  <div id="app" @click="mostrandoBloqueDonacion=false">
    <div id="titulo">
      <h1>Aves Maestras</h1>
      
    </div>
    <div id="zonaVideo">
        <!-- <video controls src="https://youtu.be/um-pobNK9H4" id="videoPresentacion">Video no compatible</video> -->
        <iframe src="https://www.youtube.com/embed/um-pobNK9H4" id="videoPresentacion" title="Video promocional" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope;" allowfullscreen></iframe>
      </div>
    <div id="bloqueDonacion" @click.stop="" :style="[offsetBloqueDonaciones]">
      <div id="cartelDonacion">
        <img src="@/assets/aportarDonacion.png" width="60px" alt="Aportar" title="¡Quiero apoyar este proyecto!" id="imagenAportarDonacion" @click.stop="mostrandoBloqueDonacion=true">
      </div>

      <div class="anuncio" id="anuncioRegalo">
        ¡En agradecimiento por tu apoyo puedes recibir de nuestra parte uno de estos
        objetos!
      </div>

      <div id="listaRegalos">
        <img src="@/assets/manilla.png" :style="{backgroundColor: mostrandoInfoRegalo==='manillas'?'#06060645':''}" width="90" alt="Manilla" class="regalo" @click="mostrandoInfoRegalo='manillas'">
        <!-- <img src="@/assets/lapiz.png" :style="{backgroundColor: mostrandoInfoRegalo==='lapiz'?'#06060645':''}" width="90" alt="Lapiz artesanal" class="regalo" @click="mostrandoInfoRegalo='lapiz'"> -->
        <div class="informacionRegalo" id="informacionManillas" v-show="mostrandoInfoRegalo==='manillas'">
          ¡Un combo de tres manillas!
        </div>
        <!-- <div class="informacionRegalo" id="informacionManillas" v-show="mostrandoInfoRegalo==='lapiz'">
          ¡Un lápiz con un muñequito en el borrador!
        </div> -->
      </div>

      <div id="bloqueContactoDonacion">
        <div class="anuncio">
          Para realizar tu donación comunicate con:
        </div>
        <div id="bloqueReceptorDonaciones">
          <img src="@/assets/receptorDonaciones.png" alt="Responsable" title="¡El encargado de las donaciones!" width="60" id="receptorDonaciones">
          <div id="infoContactoReceptorDonaciones">
            <div id="nombreReceptorDonaciones">Laura Victoria Mamián López</div>
            <div id="wsReceptorDonaciones"> <img width="20" src="@/assets/iconoWs.png" alt="Whatsapp"> 3216436869</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      mostrandoBloqueDonacion:false,
      mostrandoInfoRegalo:'manillas'
    }
  },
  computed:{
    offsetBloqueDonaciones(){
      if(this.mostrandoBloqueDonacion){
        return {
          top: '20%'                
        }
      }
      return{
        top:'100vh'
      }
      
    }
  }
}
</script>

<style>
body{
  background-color: #2e9d88;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}
#titulo{
  color: #141b22;
}
#zonaVideo{
  height: 70vh;
}
#videoPresentacion{
  height: 100%;
  width: 100%;
}
#imagenAportarDonacion{
  border: 1px solid black;
  border-radius: 50%;
  cursor: pointer;
  background-color: #50efff;
  display: block;
  margin: 0px auto;
}
#bloqueDonacion{
  position: fixed;
  left: 50%;
  transform: translateX(-50%);
  border: 2px solid rgb(33, 85, 87);
  background-color: #2b8993;
  border-radius: 40px;
  width: min(500px, 90%);
  transition: top 1s, bottom 1s;
}
#cartelDonacion{
  position: absolute;
  bottom: 105%;
  left: 50%;
  transform: translateX(-50%);
}

#anuncioRegalo{
  margin-top: 20px;
  padding: 0px 30px;
}
.regalo{
  border: 1px solid cadetblue;
  border-radius: 50%;
  cursor: pointer;
  margin: 0px 20px;
}
.regalo:hover{
  background-color: rgba(128, 128, 128, 0.151);
}
.informacionRegalo{
  padding: 5px;
  border: 1px solid #d4c2b4;
  border-radius: 15px;
  margin: 10px 10%;
  margin-bottom: 40px;
  background-color: #06060645;
  color: white;
}
#bloqueReceptorDonaciones{
  display: flex;
  padding: 10px 30px;
  border-radius: 50px;
  background-color: #c14e4e;
  margin: 20px 50px;
}

#receptorDonaciones{
  border-radius: 50%;
}
</style>
