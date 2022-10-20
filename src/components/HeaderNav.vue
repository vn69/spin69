<template>
  <div>
    <nav class="text-end">
      <a href="#" @click="open">
        <i class="el-icon-menu"></i>
      </a>
    </nav>
    <el-drawer :visible.sync="drawer" :with-header="false">
      <div class="nav_menu text-center p-2">
        <div class="text-right" @click="close">
          <i class="el-icon-close mb-3"></i>
        </div>
        <div @click="close" class="mb-3">
          <router-link to="/">Home</router-link>
        </div>
        <div @click="close" class="mb-3">
          <router-link to="/About">About</router-link>
        </div>
        <div @click="close" class="mb-3">
          <router-link to="/Spin">Spin</router-link>
        </div>
      </div>
    </el-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
    };
  },
  methods: {
    open() {
      this.drawer = true;
    },
    close() {
      this.drawer = false;
    },
  },
};
</script>

<style lang="scss">
nav {
  padding: 10px;
  position: absolute;
  top: 0;
  width: 100%;
  background-color: white;
  z-index: 1;
  a {
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
