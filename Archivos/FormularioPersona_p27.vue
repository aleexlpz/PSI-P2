<!-- FormularioPersona.vue -->
<template>
  <!-- Contenedor principal del componente -->
  <div id="formulario-persona">
    <!-- Formulario con campos para ingresar informacion de una persona -->
    <form>
      <div class="container">
        <!-- Primera fila con campos de nombre, apellido y email -->
        <div class="row">
          <div class="col-md-4">
            <div class="form-group">
              <!-- Etiqueta y campo de entrada para el nombre con binding bidireccional v-model -->
              <label>Nombre</label>
              <input v-model="persona.nombre" type="text" class="form-control" />
            </div>
          </div>
          <div class="col-md-4">
            <div class="form-group">
              <!-- Etiqueta y campo de entrada para el apellido con binding bidireccional v-model -->
              <label>Apellido</label>
              <input v-model="persona.apellido" type="text" class="form-control" />
            </div>
          </div>
          <div class="col-md-4">
            <div class="form-group">
              <!-- Etiqueta y campo de entrada para el correo electronico con binding bidireccional v-model -->
              <label>Email</label>
              <input v-model="persona.email" type="email" class="form-control" />
            </div>
          </div>
        </div>
        <!-- Segunda fila con un boton para agregar persona -->
        <div class="row">
          <div class="col-md-4">
            <div class="form-group">
              <!-- Boton para agnadir persona -->
              <button class="btn btn-primary">Agnadir persona</button>
            </div>
          </div>
        </div>
      </div>
    </form>
  </div>
</template>

<script setup>
// Importacion de la funcion "ref" de Vue 3
import { ref } from 'vue';

// definicion del componente
defineOptions({
    // nombre del componente
    name: 'formulario-persona',
});

// Declaracion de una variable reactiva "persona" con propiedades nombre, apellido y email
const persona = ref({
    nombre: '',
    apellido: '',
    email: '',
});
</script>

<style scoped>
/* Estilos especificos del componente con el modificador "scoped" */
form {
    margin-bottom: 2rem;
}
</style>  