<template>
  <v-app>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
	transition: {
		name: 'page',
		model: 'out-in',
	},
  data() {
    return {
    }
  }
}
</script>
