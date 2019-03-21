<template>
	<header>
		 <section class="header-content">
      <!-- <img src="images/rocky-dashed.svg" class="rocky-dashed"> -->
      <h1 class="header-title">Your awesome landing page</h1>
      <h3 class="header-subtitle">A useful start for your projects</h3>
      <p class="header-button"><a href="#calls-to-action" class="button">Get started today</a></p>
    </section>
	</header>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  }
}
</script>

<style lang="stylus" scoped>
header 
	align-items: center;
</style>

