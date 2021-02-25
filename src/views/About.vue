<template>
  <div class="about">
    <div class="text-dark">
      <div>⠀</div>
    </div>
    <div class="row">
      <product
        v-for="(item, index) in sendData"
        :key="index"
        :NameProduct="item.NameProduct"
        :img="item.img"
        :Price="item.Price"
        @Order="menuOrder"
      />
    </div>
  </div>
</template>
<script>
import Product from "../components/Product.vue";
import { mapGetters } from "vuex";

export default {
  components: { Product },
  computed: {
    ...mapGetters(["sendData","menuOrder"])
  }
};
</script>
<style></style>
