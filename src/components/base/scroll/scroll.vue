<template>
  <div ref="rootRef">
    <slot></slot>
  </div>
</template>

<script>
  import useScroll from './useScroll'
  import { ref } from 'vue'

  export default {
    name: 'scroll',
    props: {
      click: {
        type: Boolean,
        default: true
      },
      probeType: {
        type: Number,
        default: 0
      }
    },

    setup(props) {
      const rootRef = ref(null)
      const scroll = useScroll(rootRef, props)

      return {
        rootRef,
        scroll
      }
    }
  }
</script>
