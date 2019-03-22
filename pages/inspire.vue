<template>
  <div>
    <!-- 顶部菜单 -->
    <my-toolbar @clickMenu="drawer = !drawer"></my-toolbar>
    <!-- 侧部菜单 -->
    <my-nav :drawer.sync="drawer">
      <</my-nav> <!-- 内容区域 -->
        <v-container>
          <v-layout wrap row>
            <v-flex text-xs-center sx12 sm6 v-for="item in items" :key="item.headlineText">
              <v-card class="ma-2" :height="580">
                <v-img class="py-4" :src="item.image" aspect-ratio="1"></v-img>
                <v-card-title primary-title>
                  <div>
                    <h3 class="headline mb-0">{{item.headlineText}}</h3>
                    <div> {{ item.mainText }} </div>
                  </div>
                </v-card-title>

                <v-card-actions>
                  <v-btn flat color="orange">购买</v-btn>
                  <v-btn flat color="orange">详情</v-btn>
                </v-card-actions>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>

  </div>
</template>

<script>
  import myNav from '@/components/MyNav.vue';
  import myToolbar from '@/components/MyToolbar.vue';

  import testImg from '@/assets/image/test1.jpeg';

  export default {
    components: {
      myNav,
      myToolbar,
    },
    asyncData(context) {
      return context.app.$storyapi.get('cdn/stories', {
        version: 'draft',
        starts_with: 'coffee/'

      }).then(res => {
        return {
          items: res.data.stories.map(bp => {
            return {
              id: bp.slug,
              headlineText: bp.content.title,
              mainText: bp.content.content,
              image: bp.content.thumbnail,
            }
          }),
        }
      })
    },
    mounted() {
      /* const api = this.$storyapi; */
      /* console.log({ api }) */
    },
    data() {
      return {
        drawer: false, // 是否打开侧部菜单
      }
    }
  }
</script>

<style lang="less" scoped>
</style>
