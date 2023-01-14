<template>
  <div>
    <img :src="name.image" class="room-img" />
    <h4 @click="openModal">
      {{ name.title }}
    </h4>
    <p>{{ name.price }}원</p>
  </div>
</template>

<script>
export default {
  name: "ProductList",
  props: {
    name: Object,
  },
  methods: {
    openModal() {
      this.$emit('openModal', this.name.id);
    }
  },
};
</script>

<style>
</style>