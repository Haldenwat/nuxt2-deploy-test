<template>
  <div class="homepage__hero">
    <div class="hero-img__evil-larry">
      <img src="~/assets/evil-larry-larry.png">
      <div class="homepage__stars-container"">
        <StarIcon v-for="i in 15" :key="i" />
      </div>
    </div>
  </div>
</template>

<script>
import StarIcon from '../components/StarIcon.vue';

export default {
  name: 'IndexPage'
}
</script>
<style lang="scss" scoped>
.homepage {
  &__hero {
    width: 100%;
    display: flex;
    justify-content: center;
    position: relative;
    animation: 3s infinite blur;
  }

  &__stars-container {
    width: 100%;
    position: absolute;
    top: 50%;
    left: 50%;
  }
}

@keyframes blur {
  0% {filter: blur(10px);}
  60% {filter: blur(0px);}
  100% {filter: blur(10px);}
}
</style>
