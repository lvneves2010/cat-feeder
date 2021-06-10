<template>
  <div id="Profile">
    <h1
      style="font-size: 2rem;
      font-weight: 400;
      line-height: 2.5rem;
      letter-spacing: 0;
      padding-bottom: 15px;
      text-align: start;"
    >
      Capacidade
    </h1>
    <cv-list>
      <cv-list-item
        ><strong>Situação do alimentador em 10/06/2021 </strong></cv-list-item
      >
      <cv-list-item>Capacidade Total: {{ totalCapacity }} g</cv-list-item>
      <cv-list-item
        >Total armazenado atualmente: {{ totalAvailable }} g</cv-list-item
      >
      <cv-list-item
        >Alimento disponível:
        {{ ((totalAvailable / totalCapacity) * 100).toFixed(1) }}
        %</cv-list-item
      >
      <cv-list-item
        >Consumo diário recomendado: {{ dailyTarget }} g</cv-list-item
      >
      <cv-list-item
        >Autonomia:
        {{ (totalAvailable / dailyTarget).toFixed(1) }} dias</cv-list-item
      >
    </cv-list>
  </div>
</template>
<script>
export default {
  name: "Profile",
  props: ["dailyTarget"],
  data() {
    return {
      totalCapacity: 1000,
      totalAvailable: 575
    };
  }
};
</script>
<style>
#Profile {
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
  #Profile {
    display: block;
  }
}
</style>
