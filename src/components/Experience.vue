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
    <cv-list v-if="!editing">
      <cv-list-item>Proteina Bruta: {{ protein }} g</cv-list-item>
      <cv-list-item>Extrato etéreo: {{ eter }} g</cv-list-item>
      <cv-list-item>Extrato não nitrogenado: {{ nitro }} g</cv-list-item>
    </cv-list>
    <cv-list v-else>
      <cv-list-item>Proteina Bruta: <input id="protein" v-model="protein" /> g</cv-list-item>
      <cv-list-item>Extrato etéreo: <input id="eter" v-model="eter" /> g</cv-list-item>
      <cv-list-item>Extrato não nitrogenado: <input id="nitro" v-model="nitro" /> g</cv-list-item>
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

    <cv-list v-if="!editing">
      <cv-list-item>Idade: {{ age }} anos</cv-list-item>
      <cv-list-item>Peso: {{ weight }} Kg</cv-list-item>
      <cv-list-item>qtde diaria: {{ dailyTarget }} g</cv-list-item>
      <cv-list-item>Sexo: {{ gender }}</cv-list-item>
    </cv-list>
    <cv-list v-else>
      <cv-list-item>Idade: <input id="age" v-model="age"/> anos</cv-list-item>
      <cv-list-item>Peso: <input id="weight" v-model="weight" /> Kg</cv-list-item>
      <cv-list-item>Sexo: <input id="gender" v-model="gender" /></cv-list-item>
    </cv-list>
    <cv-button v-if="!editing" style="margin=10px" @click="editInfo">Editar</cv-button>
    <cv-button v-else style="margin=10px" @click="saveInfo">Salvar</cv-button>
  </div>
</template>
<script>
export default {
  name: "Education",
  data() {
    return {
      editing: false,
      protein: 100,
      nitro: 0,
      eter: 0,
      age: 4,
      weight: 4,
      gender: "macho",
      dailyTarget: 0
    };
  },
  methods: {
    editInfo() {
      this.editing = true;
    },
    saveInfo() {
      this.editing = false;
      this.dailyTargetCalc();
      this.$emit("emitDailyTarget", this.dailyTarget);
    },
    dailyTargetCalc() {
      this.dailyTarget =
        ((this.age * this.weight) / (this.protein + this.nitro + this.eter)) *
        1000;
      return this.dailyTarget;
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
