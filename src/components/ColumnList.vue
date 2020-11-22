<template>
  <div class="container">
    
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export interface columnProps {
  id: Number,
  title: String,
  avatar: String,
  desc: String
}
export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array,
      required: true
    }
  }
})
</script>
