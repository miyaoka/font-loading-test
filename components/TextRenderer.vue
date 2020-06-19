<template>
  <div :style="style" class="text"><slot /></div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    family: {
      type: String,
      default: '',
    },
    weight: {
      type: String,
      default: '400',
    },
  },
  computed: {
    style(): Record<string, string> {
      return {
        fontFamily: `'${this.family}'`,
        fontWeight: this.weight,
      }
    },
  },
})
</script>

<style scoped>
.text {
  border: 1px solid #999;
  padding: 20px;
}
</style>
