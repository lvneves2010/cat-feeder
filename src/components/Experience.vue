<template>
  <div id="Experience">
    <h1
      style="font-size: 2rem;
    font-weight: 400;
    line-height: 2.5rem;
    letter-spacing: 0;
    padding-bottom: 15px;
    text-align: start;"
    >
      Informações da Ração
    </h1>
    <cv-list>
      <cv-list-item>Proteina Bruta: {{protein}} g</cv-list-item>
      <cv-list-item>Extrato etéreo: {{eter}} g</cv-list-item>
      <cv-list-item>Extrato não nitrogenado: {{nitro}} g</cv-list-item>
    </cv-list>

    <h1
      style="font-size: 2rem;
    font-weight: 400;
    line-height: 2.5rem;
    letter-spacing: 0;
    padding-bottom: 15px;
    text-align: start;"
    >
      Informações do animal
    </h1>

    <cv-list>
      <cv-list-item>Idade: {{age}}</cv-list-item>
      <cv-list-item>Peso: {{weight}} Kg</cv-list-item>
      <cv-list-item>Sexo: {{gender}}</cv-list-item>
    </cv-list>
    <cv-button style="margin=10px" @click="editInfo">Editar</cv-button>
  </div>
</template>
<script>
export default {
  name: "Education",
  props: {
    portugues: {
      type: Boolean
    }
  },
  data() {
    return {
      protein: 0,
      nitro: 0,
      eter: 0,
      age: 0,
      weight: 0,
      gender: "macho"
    };
  },
  methods: {
    editInfo() {
      this.telaPrincipal = !this.telaPrincipal;
    }
  }
};
</script>
<style>
#Experience {
  display: flex;
  justify-content: center;
  margin: 10px;
  padding-top: 15px;
  border-bottom-style: solid;
  border-bottom-color: black;
  border-bottom-width: 0.5px;
  padding-bottom: 15px;
}
@media screen and (max-width: 900px) {
  #Experience {
    display: block;
  }
}
</style>
