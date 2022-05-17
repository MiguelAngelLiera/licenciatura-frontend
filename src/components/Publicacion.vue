<template>
    <div>
    <section>
        <div class="card my-card" >
            <div class=card-header>
                <h2>Publicación</h2>
            </div>
            <div class="card-body">
                <label>
                    Texto
                    <input type="text" v-model="texto" class="form-control"/>
                </label>
                
                <button class="btn btn-primary mb-2" v-on:click="publicar">Publicar</button>
            </div>
        </div>
        <b-modal id="error" :title="titulo_error">
            <p>{{msj_error}}</p>
        </b-modal>
        <b-modal id="aviso" :title="titulo_aviso" @hidden="borrarMensaje">
            <p>{{body_aviso}}</p>
        </b-modal>
    </section>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Publicacion',
    components: {

    },
    data: function(){
        return {
            texto: "",

        }
    },
    components: {

    },
    methods: {
        publicar(){
          axios.post(SERVER + '/usuario/publicacion/', {
                texto: this.texto,
          }).then(response => {
                
            }).catch(error => {
                
           });

        }
    }
}
</script>

<style scoped>
  html, body {
    margin: 0;
    padding: 0;
  }
  
      .my-card{
          width: 40vw;
      }
  
      section {
          width: 100%;
          height: 92vh;
          min-height: 400px;
          display: flex;
          background-color: gainsboro;
          align-items: center;
          justify-content: center;
      }
      label{
          display: block;
      }
      input {
          width: 100%;
      }
      h2 {
          text-align: center;
      }
      button {
          margin-top: 2%;
      }
      .footer {
          display: flex;
          align-items: center;
          justify-content: center;
          flex-wrap: wrap;
  
      }
      .footer a{
          margin-right: 4%;
          flex: 120px;
          text-align: center;
          text-decoration: none;
      }
      @media (max-width: 1300px) {
          .my-card{
              width: 80vw;
          }
      }
</style>