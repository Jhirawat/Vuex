<template>
  <div>
    <input
      type="text"
      class="form-control"
      placeholder="ชื่อสิ้นค้า"
      v-model="Name"
    />
    <input type="text" class="form-control" placeholder="รูป" v-model="img" />
    <input
      type="text"
      class="form-control"
      placeholder="ราคา"
      v-model="Price"
    />
    <button type="button" class="btn btn-outline-info" @click="OrderAdmin()">
      <b-icon icon="Tools"></b-icon>สร้าง
    </button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      Name: "",
      img : "",
      Price: 0
    };
  },
  methods: {
    OrderAdmin() {
      alert("สร้างเรียบร้อย");
      this.$emit("OrderAdmin", {
        NameProduct: this.Name,
        Price: this.Price,
        img: this.img
      });
    }
  }
};
</script>
