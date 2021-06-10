<template>
  <div id="Presentation">
    <div id="side" class="bx--col-md-8">
      <transition name="slide" appear>
        <img
          style="border-radius: 70px; max-height: 150px;"
          src="../assets/cat_food.png"
          alt="profile-picture"
        />
      </transition>
    </div>
    <div id="main">
      <H1>Alimentador para Gatos</H1>
    </div>
  </div>
</template>
<script>
export default {
  name: "Presentation",
  props: {}
};
</script>
<style>
#Presentation {
  border-bottom-style: solid;
  border-bottom-color: black;
  border-bottom-width: 0.5px;
  padding-bottom: 15px;
}
#main {
  /* text-align: start; */
  vertical-align: top;
  font-size: 24px;
}

@keyframes slide-in {
  from {
    transform: translateX(-400px);
  }
  to {
    transform: translateX(0px);
  }
}

@keyframes slide-out {
  from {
    transform: translateY(0px);
  }
  to {
    transform: translateY(40px);
  }
}

.slide-enter-active {
  animation: slide-in 8s ease;
  transition: opacity 8s;
}

.slide-enter {
  opacity: 0;
}
</style>
