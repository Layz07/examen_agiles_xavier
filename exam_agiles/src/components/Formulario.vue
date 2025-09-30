<template>
  <div class="formulario">
    <h2>Registro</h2>
    <form @submit.prevent="enviarFormulario">
      <div>
        <label for="nombre">Nombre:</label>
        <input type="text" v-model="form.nombre" id="nombre" />
      </div>

      <div>
        <label for="email">Email:</label>
        <input type="email" v-model="form.email" id="email" />
      </div>

      <div>
        <label for="edad">Edad:</label>
        <input type="number" v-model="form.edad" id="edad" />
      </div>

      <button type="submit">Enviar</button>
    </form>

    <div v-if="mensaje">
      <p><strong>{{ mensaje }}</strong></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Formulario",
  data() {
    return {
      form: {
        nombre: "",
        email: "",
        edad: "",
      },
      mensaje: "",
    };
  },
  methods: {
    enviarFormulario() {
      this.mensaje = `Formulario enviado: ${this.form.nombre}, ${this.form.email}, ${this.form.edad} años.`;
    },
  },
};
</script>

<style scoped>
.formulario {
  max-width: 400px;
  margin: auto;
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 10px;
}

label {
  display: block;
  margin-top: 10px;
}

input {
  width: 100%;
  padding: 6px;
  margin-top: 5px;
  border-radius: 5px;
  border: 1px solid #aaa;
}

button {
  margin-top: 15px;
  padding: 8px 15px;
  border: none;
  background: #42b983;
  color: white;
  border-radius: 5px;
  cursor: pointer;
}
</style>
