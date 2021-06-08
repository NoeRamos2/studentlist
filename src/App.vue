<template>
  <div class="container" id="app">
    <h2>App.vue</h2>
    <h3>{{ titulo }}</h3>
    <div class="container">
      <div class="form">
        <div class="form-group">
          <label>Nombre</label>
          <input type="text" class="form-control" v-model="registro.nombre" />
        </div>
        <div class="form-group">
          <label>Colegio</label>
          <input type="text" class="form-control" v-model="registro.colegio" />
        </div>
        <button class="btn btn-primary" @click="agregar">Guardar</button>
      </div>
      <div class="row">
        <div class="col-5" v-for="(registro, index) in registros" :key="index">
          <div class="card">
            <div class="form-group">
              <h2>{{index}}</h2>
              <h2>{{ registro.nombre }}</h2>
              <h2>{{ registro.colegio }}</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
    <br>
  </div>
</template>

<script>

export default {
  
  components: { 

  },
  name: "App",
  data() {
    return {
      titulo: "Lista",
      registro: {
        nombre: "",
        colegio: "",
      },
      registros: [
        {
          nombre: "Noe",
          colegio: "UMAR",
        },
      ],
    };
  },
  methods: {
    agregar: function () {
      const { nombre, colegio } = this.registro;
      this.registros.push({ nombre, colegio });
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h2{
  color: black;
}
</style>
