<template>
    <v-toolbar>
      <v-toolbar-side-icon @click="menuClick" />
      <v-toolbar-title>SS咖啡馆</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-and-down">
        <v-text-field label="查询您想要的商品" v-model="searchText" append append-icon="search" hide-details single-line></v-text-field>
      </v-toolbar-items>
    </v-toolbar>
</template>

<script>
	export default {
		name: '',
		props: ["search"],
		computed: {
			searchText: {
				get() {
					return this.search;
				},
				set(val) {
					this.$emit("update:search", val);
				}
			}
		},
		data() {
			return {
        /* searchText: '', */
			}
		},
		methods: {
			menuClick() {
				this.$emit('clickMenu');
			},
		},
	};
	</script>

<style lang="less" scoped>
</style>

