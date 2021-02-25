<template>
  <div class="home">
    <users :Total="Total" :Data="Data" />
    <table class="table">
      <thead class="thead-dark">
        <tr>
          <th scope="col">ชื่อสินค้า</th>
          <th scope="col">ราคา</th>
          <th scope="col">จำนวน</th>
          <th scope="col">รวม</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(mi, index) in sendSelect" :key="index">
          <td>{{ mi.NameProduct }}</td>
          <td>{{ mi.Price }}</td>
          <td>{{ mi.Amount }}</td>
          <td>{{ mi.Total }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
// @ is an alias to /src
import Users from "../components/Users.vue";
import { mapGetters } from "vuex";

export default {
  name: "Home",
  components: {
    Users
  },
  computed: {
    ...mapGetters(["sendSelect"])
  },
  props: {
    Total: Number
  }
};
</script>
