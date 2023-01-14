<template>
  <div class="black-bg" v-if="modal == 1">
    <div class="white-bg">
      <img :src="onerooms[id].image" />
      <h4>{{ onerooms[id].title }}</h4>
      <p>{{ onerooms[id].content }}</p>
      <p>가격 : {{ onerooms[id].price }}</p>
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {};
  },
  props: {
    onerooms: Object,
    id: Number,
    modal: Number,
  },
  methods: {
    closeModal() {
      this.$emit('closeModal')
    },
  },
};
</script>

<style>
</style>