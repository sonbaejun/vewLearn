<template>
  <div class="black-bg" v-if="modal == 1">
    <div class="white-bg">
      <img :src="onerooms[id].image" />
      <h4>{{ onerooms[id].title }}</h4>
      <p>{{ onerooms[id].content }}</p>
      <input v-model="month" placeholder="개월 수를 입력하세요." />
      <p>{{ month }}개월: {{ onerooms[id].price * month }}원</p>
      <button @click="closeModal">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      month: "1",
    };
  },
  watch: {
    /* 감시할 데이터를 함수명으로, 두개의 파라미터 가능(변경 후 데이터, 변경 전 데이터) */
    month(a) {
      if(a > 12) {
        alert('12개월까지만 가능합니다');
        this.month = 1;
      }
      const reg = /[ㄱ-ㅎ|ㅏ-ㅣ|가-힣|a-z]/g;
      if (reg.exec(a) !== null) {
        alert('숫자만 입력해주세요!');
        this.month = 1;
      }
    },
  },
  props: {
    onerooms: Object,
    id: Number,
    modal: Number,
  },
  methods: {
    closeModal() {
      this.$emit("closeModal");
    },
  },
};
</script>

<style>
</style>