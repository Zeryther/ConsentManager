<template>
  <div class="consentmanager__selection">
    <div class="consentmanager__selection__heading">
      Wählen Sie Ihre Präferenz
    </div>
    <div class="consentmanager__selection__list">
      <Category v-for="category of categories" :key="category.name" :category="category"/>
    </div>

    <div class="consentmanager__selection__actions">
      <button class="consentmanager-button" @click="$parent.apply()">Auswahl speichern</button>
      <button class="consentmanager-button primary" @click="$parent.acceptAll() || $parent.apply()">Alle akzeptieren</button>
    </div>
  </div>
</template>

<script>
import Category from "../Category.vue";

export default {
  components: { Category },
  name: "Settings",
  computed: {
    categories() {
      return this.$store.state.categories;
    },
  },
};
</script>