<template>
  <div id="translateForm">
    <form v-on:submit="formSubmit">
      <input type="text" v-model="textToTranslate" placeholder="Enter a word" />
      <select v-model="language">
        <option value="ru">Russain</option>
        <option value="es">Spainish</option>
        <option value="fr">French</option>
        <option value="de">Deutch</option>
      </select>
      <input type="submit" value="Translate" />
    </form>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data() {
    return {
      textToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "de";
  },
  methods: {
    formSubmit(e) {
      e.preventDefault();
      this.$emit("formSubmit", this.textToTranslate, this.language);
    }
  }
};
</script>

<style>
</style>
