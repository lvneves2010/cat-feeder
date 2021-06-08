<template>
  <cv-footer class="header" aria-label="Carbon Footer">
    <cv-footer-name href="javascript:void(0)">
      Projeto Integrador - Equipe: Guarulhos 1 - 4N.1
    </cv-footer-name>
  </cv-footer>
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
