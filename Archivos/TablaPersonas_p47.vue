<!-- src/components/TablaPersonas.vue -->
<template>
  <div id="tabla-personas">
    <div v-if="!personas.length" class="alert alert-info" role="alert">
      No se han encontrado personas
    </div>
    <div v-else>
      <table class="table">
        <thead>
          <tr>
            <th>Nombre</th>
            <th>Apellido</th>
            <th>Email</th>
            <th>Acciones</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="persona in personas" :key="persona.id">
            <td>{{ persona.nombre }}</td>
            <td>{{ persona.apellido }}</td>
            <td>{{ persona.email }}</td>
            <td>
              <button
                class="btn btn-info"
                data-cy="edit-button"
                @click="editarPersona(persona)"
              >
                ✏️ Editar
              </button>
              <button
                class="btn btn-danger ml-2"
                data-cy="delete-button"
                @click="$emit('delete-persona', persona.id)"
              >
                🗑️ Eliminar
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  defineOptions({
    name: 'tabla-personas',
  });

  const props = defineProps({
    personas: {type: Array, default: []},
  });
  const emit = defineEmits(['delete-persona']);

  const editando = ref(null);
  const personaEditada = ref(null);

  const editarPersona = (persona) => {
    personaEditada.value = { ...persona };
    editando.value = persona.id;
  };
</script>

<style scoped>
  /* Estilos especificos del componente con el modificador "scoped" */
</style>
