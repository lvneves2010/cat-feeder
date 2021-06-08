<template>
  <div id="Profile">
    <h1
      v-if="!portugues"
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
      <cv-list-item>Capacidade Total: 1000g</cv-list-item>
      <cv-list-item>Total armazenado atualmente: 575g</cv-list-item>
      <cv-list-item>Alimento disponível: 57%</cv-list-item>
    </cv-list>
  </div>
</template>
<script>
export default {
  name: "Profile",
  props: {
    portugues: {
      type: Boolean
    }
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
