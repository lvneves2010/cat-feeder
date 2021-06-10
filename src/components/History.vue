<template>
  <div id="History">
    <h1
      style="font-size: 2rem;
      font-weight: 400;
      line-height: 2.5rem;
      letter-spacing: 0;
      padding-bottom: 15px;
      text-align: start;"
    >
      Histórico
    </h1>
    <cv-list>
      <p>Ultimas variações</p>
      <cv-list-item>10/06/2021 - 17:00 : 85g</cv-list-item>
      <cv-list-item>10/06/2021 - 12:30 : 105g</cv-list-item>
      <cv-list-item>09/06/2021 - 17:00 : 65g</cv-list-item>
      <cv-list-item>09/06/2021 - 11:00 : 95g</cv-list-item>
      <cv-list-item>08/06/2021 - 19:00 : 75g</cv-list-item>
      <br /><br />
    </cv-list>
  </div>
</template>
<script>
export default {
  name: "History",
  props: {}
};
</script>
<style>
#History {
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
  #History {
    display: block;
  }
}
.cv-list {
  padding: 25px;
}
</style>
