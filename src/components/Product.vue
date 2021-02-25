<template>
    <div class="col-lg-3">
      <b-card
        border-variant="dark"
        :header="NameProduct"
        header-bg-variant="dark"
        header-text-variant="white"
        align="center"
        style="height: 40rem"
        ><b-col md="12">
          <b-card-img :src="img" alt="Image" class="rounded-0"  height="400"></b-card-img>
        </b-col>
        <b-card-text>ราคาเล่มละ : {{ Price }} บาท</b-card-text>
        จำนวน
        <b-form-spinbutton
          id="sb-small"
          size="sm"
          v-model="Amount"
          class="mb-2"
        ></b-form-spinbutton>
        <button type="button" class="btn btn-outline-info" @click="Order()">
          <b-icon icon="basket2-fill"></b-icon> จัดซื้อ
        </button>
      </b-card>
      <div>
        ⠀
      </div>
    </div>
</template>
<script>
export default {
  props: {
    NameProduct: String,
    img: String,
    Price: Number
  },
  data() {
    return {
      Amount: 1
    };
  },
  methods: {
    Order() {
      alert("เรียบร้อย");
      this.$emit("Order", {
        NameProduct: this.NameProduct,
        Price: this.Price,
        Amount: this.Amount,
        Total: this.Price * this.Amount
      });
    }
  }
};
</script>
<style></style>
