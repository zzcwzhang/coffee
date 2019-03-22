<template>
  <v-navigation-drawer v-model="cdrawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
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
		<v-treeview class="ml-4" :items="tree"></v-treeview>
    </v-list>

  </v-navigation-drawer>
</template>

<script>
  export default {
    name: '',
		props: ['drawer'],
		computed: {
			cdrawer: {
				get() {
					return this.drawer;
				},
				set(val) {
					this.$emit('update:drawer', val);
				}
			}
		},
		data() {
			return {
        miniVariant: false,
        clipped: false,
				tree: [
					{
						id: 1,
						name: '女鞋',
						children: [
							{ id: 2, name: '草鞋' },
							{ id: 3, name: '皮靴' },
						]
					},
					{
						id: 100,
						name: '包',
						children: [
							{ id: 102, name: '背包' },
							{ id: 103, name: '挎包' },
						]
					},
				],
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
			}
		}
  };
</script>

<style lang="less" scoped>
  .gradientText {
    font-size: 200px;
  }
</style>
