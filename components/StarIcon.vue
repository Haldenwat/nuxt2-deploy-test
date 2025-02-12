<template>
  <div class="star-icon__container" :style="style">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="20"
      height="20"
      viewBox="0 0 20 20"
      fill="none"
    >
      <path
        d="M10.0166 16.1273L5.2027 19.772C4.97122 19.9415 4.7342 20.0165 4.49164 19.997C4.2491 19.9775 4.02741 19.9025 3.82656 19.772C3.62571 19.6415 3.48273 19.4631 3.39763 19.2368C3.31252 19.0105 3.30486 18.7626 3.37467 18.4931L5.21289 12.5372L0.503673 9.15183C0.272192 8.9908 0.120924 8.79291 0.0498709 8.55816C-0.0212019 8.32339 -0.0163084 8.09498 0.0645514 7.87294C0.145392 7.66191 0.273679 7.47376 0.449414 7.30848C0.625168 7.14322 0.864958 7.06059 1.16878 7.06059H6.99879L8.883 0.841587C8.95278 0.561048 9.09576 0.350654 9.31193 0.210404C9.5281 0.0701343 9.75746 0 10 0C10.2425 0 10.4719 0.0701343 10.6881 0.210404C10.9042 0.350654 11.0528 0.561048 11.1336 0.841587L13.0012 7.06059H18.8478C19.1406 7.06059 19.3748 7.14322 19.5506 7.30848C19.7263 7.47376 19.8546 7.66191 19.9354 7.87294C20.0163 8.09498 20.0212 8.32339 19.9501 8.55816C19.8791 8.79291 19.7278 8.9908 19.4963 9.15183L14.7871 12.5372L16.6253 18.4766C16.6951 18.7571 16.6875 19.0077 16.6024 19.2285C16.5173 19.4493 16.3743 19.6249 16.1734 19.7554C15.9726 19.897 15.7537 19.9775 15.5166 19.997C15.2796 20.0165 15.0454 19.936 14.8139 19.7554L10.0166 16.1273Z"
        fill="#00ACFF"
      />
    </svg>
  </div>
</template>
<script setup>
const angle = Math.random() * Math.PI * 2
const startX = Math.cos(angle) * 90 + Math.random() * 230 - 115
const startY = Math.sin(angle) * 250 - 100
const scale = Math.random() + 0.5
const duration = Math.random() * 2 + 1

const style = `transform: translate(${startX}px, ${startY}px) scale(${scale});--startX: ${startX}px; --startY: ${startY}px; --duration: ${duration}s; --scale: ${scale};`
</script>
<style lang="scss" scoped>
.star-icon {
  &__container {
    position: absolute;
    opacity: 0;
    animation: grow var(--duration) linear infinite;
  }

  @keyframes grow {
    0% {
      opacity: 0;
    }
    60% {
      opacity: 1;
    }
    80% {
      opacity: 1;
    }
    100% {
      opacity: 0;
      transform: translate(var(--startX), var(--startY))
        scale(calc(var(--scale) * 2));
    }
  }
}
</style>
