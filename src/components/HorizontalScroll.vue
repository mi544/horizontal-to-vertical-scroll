<template>
  <div
    class="outer-container"
    :style="{ '--dynamic-height': dynamicHeight + 'px' }"
  >
    <div class="inner-container-sticky" ref="containerSticky">
      <div
        class="translate-container"
        ref="containerTranslate"
        :style="{ '--translate-x': translateX + 'px' }"
      >
        <slot />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HorizontalScroll',
  data: () => ({
    dynamicHeight: 0,
    translateX: 0
  }),
  mounted() {
    this.handleDynamicHeight()
    window.addEventListener('resize', this.onResize)
    this.applyScrollListener()
  },
  methods: {
    onResize() {
      this.handleDynamicHeight()
    },
    calcDynamicHeight(objectWidth) {
      console.log('objectWidth', objectWidth)
      const vw100 = window.innerWidth
      console.log('vw100', vw100)
      const vh100 = window.innerHeight
      console.log('vh100', vh100)
      console.log('final dynamicHeight', objectWidth - vw100 + vh100 + 150)
      return objectWidth - vw100 + vh100 + 150
    },
    handleDynamicHeight() {
      const objectWidth = this.$refs.containerTranslate.scrollWidth
      this.dynamicHeight = this.calcDynamicHeight(objectWidth)
    },
    applyScrollListener() {
      window.addEventListener('scroll', () => {
        const offsetTop = -this.$refs.containerSticky.offsetTop
        this.translateX = offsetTop
      })
    }
  }
}
// const objectWidth = this.$refs.abc.scrollWidth
// const vw100 = window.innerWidth
// const vh100 = window.innerHeight
// return objectWidth - vw100 + vh100 + 150
</script>

<style lang="scss">
.outer-container {
  height: var(--dynamic-height);
  position: relative;
  width: 100%;
}
.inner-container-sticky {
  position: sticky;
  top: 0;
  height: 100vh;
  width: 100%;
  overflow-x: hidden;
}

.translate-container {
  transform: translateX(var(--translate-x));
  position: absolute;
  height: 100%;
  will-change: transform;
}
</style>
