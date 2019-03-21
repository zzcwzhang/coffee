<template>
  <div>
    <v-toolbar>
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title>SS咖啡馆</v-toolbar-title>
			<v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-and-down">
        <v-text-field v-model="searchText" append append-icon="search" hide-details single-line></v-text-field>
      </v-toolbar-items>
    </v-toolbar>
    <v-layout>
      <v-flex text-xs-center>
        <img src="/v.png" alt="Vuetify.js" class="mb-5">
        <blockquote class="blockquote">
          &#8220;First, solve the problem. Then, write the code.&#8221;
          <footer>
            <small>
              <em>&mdash;John Johnson</em>
            </small>
          </footer>
        </blockquote>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        searchText: '',
      }
    }
  }
</script>
