<template>
  <div id="app">
    <transition name="fade" appear>
      <Header @portuguese="changeLanguage" />
    </transition>
    <transition name="fade" appear>
      <Presentation :portugues="portugues" />
    </transition>
    <transition name="fade" appear v-if="telaPrincipal">
      <Profile :portugues="portugues" />
    </transition>
    <transition name="fade" appear v-if="telaPrincipal">
      <Education :portugues="portugues" />
    </transition>
    <transition name="fade" appear v-if="!telaPrincipal">
      <Experience :portugues="portugues" />
    </transition>
    <transition name="fade" appear v-if="telaPrincipal">
      <cv-button @click="infoNutri">Informações Nutricionais</cv-button>
    </transition>
    <transition name="fade" appear v-if="!telaPrincipal">
      <cv-button @click="infoNutri">Voltar</cv-button>
    </transition>
    <transition name="fade" appear>
      <Footer @portuguese="changeLanguage" />
    </transition>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Presentation from "./components/Presentation.vue";
import Profile from "./components/Profile.vue";
import Education from "./components/Education.vue";
import Experience from "./components/Experience.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "app",
  components: {
    Header,
    Presentation,
    Profile,
    Education,
    Experience,
    Footer
  },
  data() {
    return {
      telaPrincipal: true
    };
  },
  methods: {
    infoNutri() {
      this.telaPrincipal = !this.telaPrincipal;
    }
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  $feature-flags: (
    grid-columns-16: true
  );
}

.fade-enter,
.fade1-enter,
.fade2-enter,
.fade3-enter,
.fade4-enter,
.fade5-enter,
.fade-leave-to,
.fade1-leave-to,
.fade2-leave-to,
.fade3-leave-to,
.fade4-leave-to,
.fade5-leave-to {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0s;
}
.fade1-enter-active,
.fade1-leave-active {
  transition: opacity 5s;
}
.fade2-enter-active,
.fade2-leave-active {
  transition: opacity 10s;
}
.fade3-enter-active,
.fade3-leave-active {
  transition: opacity 15s;
}
.fade4-enter-active,
.fade4-leave-active {
  transition: opacity 20s;
}
.fade5-enter-active,
.fade5-leave-active {
  transition: opacity 25s;
}
</style>
