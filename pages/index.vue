<template>
	<header class="bg">
		 <section class="header-content">
			<svg class="icon" aria-hidden="true" style="font-size: 200px; color: #fff">
				<use xlink:href="#icon-nvrenbang"></use>
			</svg>
      <h1 class="header-title">欢迎来到SS女人咖啡馆</h1>
      <h3 class="header-subtitle">轻奢 优雅 宁静 从容</h3>
			<v-btn color="info">Get started today</v-btn>
    </section>
	</header>
</template>

<script>

export default {
}
</script>

<style lang="stylus" scoped>
header 
	margin: -16px 0 0 -16px;
	align-items: center;
	background: #333;;
	display: flex;
	font-size: 18px;
	height: 100vh;
	width: 100vw;
	justify-content: center;
	overflow: hidden;
	perspective: 100px;
	position: relative;
	text-align: center;
	transform-style: preserve-3d;
	&:before
		animation: fade-slide-down 2s .5s cubic-bezier(0, 0.5, 0, 1) forwards;
		background: linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,.8)),url("../assets/image/home.jpg") no-repeat bottom; 
		background-size: cover;
		content: "";
		position: absolute;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
		z-index: -1;


	&:after 
		background: #F9FCFF;;
		content: "";
		height: 40rem;
		left: -5%;
		position: absolute;
		right: -5%;
		top: 90%;
		transform-origin: 0 0;
		transform: rotate(-4deg);

.header-title, .header-subtitle
	color: #fff;
	margin-bottom: 5rem;
	text-transform: uppercase;

.header-button
	transorm: translateZ(.1px);
	position: relative;
	z-index: 10;

@keyframes fade-slide-down {
  0% {
    opacity: 0;
    transform: translateY(-4rem);
  }
  100% {
    opacity: 1;
    transform: none;
  }
}
	
</style>

