<template>
  <Modal
    @closeModal="modal = 0"
    :onerooms="onerooms"
    :id="id"
    :modal="modal"
  ></Modal>
  <Discount />
  <div class="menu">
    <a v-for="name in menus" :key="name">{{ name }}</a>
  </div>
  <div>원룸샵</div>

  <ProductList
    @openModal="
      modal = 1;
      id = $event;
    "
    :name="onerooms[i]"
    v-for="(name, i) in onerooms"
    :key="name"
  ></ProductList>
</template>

<script>
import oneroom from "./assets/oneroom.js";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";
import ProductList from "./ProductList.vue";

export default {
  name: "App",
  data() {
    return {
      onerooms: oneroom,
      modal: 0,
      id: 0,
      declare: [0, 0, 0],
      style: "color : blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Shop", "About"],
    };
  },
  methods: {
    modalOn(i) {
      this.modal = 1;
      this.id = i;
    },
  },
  components: {
    Discount: Discount,
    Modal: Modal,
    ProductList: ProductList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
