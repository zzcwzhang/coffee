<template>
  <header :class="domCrtl">
    <section class="header-content">
      <svg class="rocky-dashed icon animate-pop-in" aria-hidden="true" style="font-size: 200px; color: #fff">
        <use xlink:href="#icon-nvrenbang"></use>
      </svg>
      <h1 class="header-title animate-pop-in">欢迎来到SS女人咖啡馆</h1>
      <h3 class="header-subtitle animate-pop-in">轻奢 优雅 宁静 从容</h3>
			<nuxt-link to="/inspire">
				<v-btn color="info" class=" animate-pop-in header-button">Get started today</v-btn>
			</nuxt-link>
    </section>
    <section class="header-down-arrow">
			<nuxt-link to="/inspire">
				<img :src="arrow" width="100" ref="bg" v-loadimg="showAnimation">
			</nuxt-link>
    </section>
  </header>
</template>

<script>
  import arrow from '@/assets/image/arrow.png';
  export default {
    directives: {
      loadimg(el, binding, vnode) {
        //el就是img
        let src = el.src
        let newImg = new Image()
        newImg.src = src
        newImg.onload = function() {
					binding.value();
        }
      }
    },
    data() {
      return {
        arrow,
        domCrtl: 'js-loading',
      }
    },
    created() {},
    mounted() {},
    methods: {
      showAnimation() {
        this.domCrtl = 'js-loaded';
      }
    },
  }
</script>

<style lang="less" scoped>
  .js-loading *,
  .js-loading *:before,
  .js-loading *:after {
		animation-play-state: paused !important;
  }

  .js-loaded header:before {
    animation: none;
  }

	a {
		text-decoration:none;
	}


  header {
    position: absolute;
    top: 0;
    left: 0;


    align-items: center;
    background: #333;
    display: flex;
    font-size: 18px;
    height: 100vh;
    width: 100vw;
    justify-content: center;
    overflow: hidden;
    perspective: 100px;
    text-align: center;
    transform-style: preserve-3d;

    &:before {
      animation: no-transform 2s .5s cubic-bezier(0, 0.5, 0, 1) forwards;
      background: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8)), url("../assets/image/home.jpg") no-repeat bottom;
      background-size: cover;
      content: "";
      transform: translateY(-4rem);
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: -1;
    }

    &:after {
      background: #F9FCFF;
      content: "";
      height: 40rem;
      left: -5%;
      position: absolute;
      right: -5%;
      top: 90%;
      transform-origin: 0 0;
      z-index: 0;
      transform: rotateZ(-4deg);
    }

    .headerBase {
      margin-bottom: 5rem;
      text-transform: uppercase;
    }

    .rocky-dashed {
      animation-delay: 1s;
    }

    .header-subtitle {
      .headerBase;
      animation-delay: 1.2s;
    }

    .header-title {
      .headerBase;
      color: #fff;
      animation-delay: 1.4s;
    }

    .header-button {
      animation-delay: 1.6s;
      transorm: translateZ(.1px);
      position: relative;
      z-index: 10;
    }
  }


  .animate-pop-in {
    animation: no-transform .6s cubic-bezier(0, 0.9, 0.3, 1.2) forwards;
    opacity: 0;
    transform: translateY(-4rem) scale(.8);
  }

  .header-down-arrow {
    position: absolute;
    bottom: 4vh;
    left: 0;
    right: 0;
    text-align: center;
    z-index: 10;

    img {
      animation: no-transform 1s 1s ease-out forwards,
        pulse 2s 3s ease-out infinite;
      opacity: 0;
      transform: translateY(4rem);
    }
  }

  @keyframes no-transform {
    100% {
      opacity: 1;
      transform: none;
    }
  }


  /* 箭头心跳动画 */
  @keyframes pulse {
    0% {
      opacity: 1;
      transform: none;
    }

    50% {
      opacity: .8;
      transform: scale(.8);
    }

    100% {
      opacity: 1;
      transform: none;
    }
  }
</style>
