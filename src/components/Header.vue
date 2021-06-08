<template>
  <cv-header class="header" aria-label="Carbon header">
    <cv-header-name href="javascript:void(0)">
      Alimentador Automático de Gatos
    </cv-header-name>
  </cv-header>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      portugues: false
    };
  },
  methods: {
    language() {
      this.portugues = !this.portugues;
      this.$emit("portuguese", this.portugues);
    }
  }
};
</script>
<style>
.header {
  display: flex;
  justify-content: space-between;
  padding: 1rem;
}

.link-blog {
  text-decoration: none;
  color: #fff;
  margin-left: 3rem;
}

.link-blog:hover {
  text-decoration: none;
  color: #fff;
}
</style>
