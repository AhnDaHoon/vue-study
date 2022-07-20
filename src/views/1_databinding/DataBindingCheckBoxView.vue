<template>
  <div>
    <div>
      <input id="html" type="checkbox" value="HTML" v-model="favoriteLang" />
      <label for="html">HTML</label>
    </div>
    <div>
      <input id="css" type="checkbox" value="CSS" v-model="favoriteLang" />
      <label for="css">CSS</label>
    </div>
    <div>
      <input id="js" type="checkbox" value="JS" v-model="favoriteLang" />
      <label for="js">JS</label>
    </div>
    <div>선택한 지역: {{ favoriteLang }}</div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      favoriteLang: []
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>

<style></style>
