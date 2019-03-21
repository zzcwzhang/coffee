<template>
  <div>
		<!-- 顶部菜单 -->
    <v-toolbar>
      <v-toolbar-side-icon @click="drawer = !drawer" />
      <v-toolbar-title>SS咖啡馆</v-toolbar-title>
			<v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-and-down">
        <v-text-field label="查询您想要的商品" v-model="searchText" append append-icon="search" hide-details single-line></v-text-field>
      </v-toolbar-items>
    </v-toolbar>
		<!-- 侧部菜单 -->
		<v-navigation-drawer
		 	v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-layout column align-center>
        <v-flex class="mt-5">
					<svg class="icon gradientText" aria-hidden="true">
						<use xlink:href="#icon-nvrenbang"></use>
					</svg>
        </v-flex>
      </v-layout>
      <v-list>
        <!-- <v-list-tile v-for="(item, i) in items" :key="i" :to="item.to" router exact> -->
        <v-list-tile v-for="(item, i) in items" :key="i" router exact>
          <v-list-tile-action>
						<svg class="icon" aria-hidden="true" style="font-size: 30px">
							<use :xlink:href="`#${item.icon}`"></use>
						</svg>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title" />
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
		</v-navigation-drawer>
		<!-- 内容区域 -->
    <v-layout>
      <v-flex text-xs-center>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        searchText: '',
        clipped: false,
        drawer: false,
        fixed: false,
        items: [{
            icon: 'icon-coffee',
            title: '咖啡',
            to: '/inspire'
          },
          {
            icon: 'icon-idea',
            title: '读物',
            to: '/'
          },
          {
            icon: 'icon-gift',
            title: '精选',
            to: '/'
          },
        ],

        miniVariant: false,
        /* right: true, */
        /* rightDrawer: false, */
        title: 'SS咖啡馆'
      }
    }
  }
</script>

<style lang="less" scoped>
.gradientText {
	font-size: 200px;
}

</style>
