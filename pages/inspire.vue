<template>
  <div>
    <!-- 顶部菜单 -->
		<my-toolbar @clickMenu="drawer = !drawer"></my-toolbar>
    <!-- 侧部菜单 -->
		<my-nav :drawer.sync="drawer" :mini-variant="miniVariant" :clipped="clipped"></my-nav>
    <!-- 内容区域 -->
    <v-layout>
      <v-flex text-xs-center>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import myNav from '@/components/MyNav.vue';
import myToolbar from '@/components/MyToolbar.vue';
  export default {
		components: {
			myNav,
			myToolbar,
		},
    data() {
      return {
        clipped: false,
        drawer: false,
        fixed: false,
        miniVariant: false,
      }
    }
  }
</script>

<style lang="less" scoped>
</style>
