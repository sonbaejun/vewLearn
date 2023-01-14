<template>
  <div class="discount">
    <h4>지금 결제하면 20% 할인</h4>
    <button @click="people++;">할인받으신분 : {{ people }}</button>
  </div>
</template>

<script>
export default {
  name: "Discount",
  data() {
    return {
      people: 0,
    };
  },
};
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5%;
}
</style>
