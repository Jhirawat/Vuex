<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-dark">
      <div id="nav">
        <router-link to="/User">
          <b-icon icon="book" style="width: 30px; height: 30px"></b-icon>
        </router-link>
        <router-link to="/"> Total-Manga Shop</router-link>
      </div>
      <div>
        <router-link to="/User">
          <button
            type="button "
            class="btn btn-outline-success mr-1"
            @click="submit"
          >
            ยืนยัน
          </button>
          <button
            type="button"
            class="btn btn-outline-danger"
            @click="clearData"
          >
            ยกเลิก
          </button>
        </router-link>
      </div>
    </nav>
    <!-- {{ sendSelect }} -->
    <router-view
      :Total="Total"
      :User="User"
      :Menuitem="Menuitem"
      :Data="Data"
      @Order="menuorder"
      @OrderAdmin="AddMenu"
    />
  </div>
</template>
<script>
import { mapGetters, mapMutations } from "vuex";

export default {
  computed: {
    ...mapGetters(["sendSelect"])
  },
  methods: {
    //คิดยอดรวมทั้งหมด
    ...mapMutations(["submit", "clearData"])
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
}

#nav {
  padding: 10px;
}

#nav a {
  font-weight: bold;
  color: #e98f29;
}

#nav a.router-link-exact-active {
  color: #e98f29;
}
</style>
