<template>
  <div class="dropdown" ref="dropDownRef">
    <a href="#" class="btn btn-outline-light dropdown-toggle my-2" @click.prevent="toggleOpen">
      {{ title }}
    </a>
    <div class="dropdown-menu" :style="{'display': 'block'}" v-if="isOpen">
      <slot></slot>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent, onMounted, onUnmounted, ref } from 'vue'
export default defineComponent({
  name: 'DropDown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup() {
    const isOpen = ref(false)
    const dropDownRef = ref<null | HTMLElement>(null)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    const handler = (e: MouseEvent) => {
      if (dropDownRef.value) {
        if (!dropDownRef.value.contains(e.target as HTMLElement) && isOpen.value) {
          isOpen.value = false
        }
      }
    }
    onMounted(() => {
      document.addEventListener('click', handler)
    })
    onUnmounted(() => {
      document.removeEventListener('click', handler)
    })
    return {
      isOpen,
      toggleOpen,
      dropDownRef
    }
  }
})
</script>
<style lang="stylus" scoped>
</style>
