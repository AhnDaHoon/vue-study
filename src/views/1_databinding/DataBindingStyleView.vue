<template>
  <div>
    <div>스타일 바인딩: 폰트크기:30px</div>
    <div
      :style="
        style1.flag === true
          ? { color: 'red', fontSize: '30px' }
          : { color: 'green', fontSize: '30px' }
      "
    >
      스타일 바인딩: green, 폰트크기:30px
    </div>
    <button
      @click="
        style1.flag === true ? (style1.flag = false) : (style1.flag = true)
      "
    >
      색상바꾸기
    </button>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      style1: {
        flag: true
      }
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
