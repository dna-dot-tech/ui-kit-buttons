<template>
    <div 
      class="button"
      :class="type"
      :disabled="disabled"
      >
        <slot></slot>
    </div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'customButton',
  props: {
    type: {
        type: String,
        default: 'default'
    },
    disabled: {
        type: Boolean,
        default: false
    }
  },
  data(){
      return{

      }
  }
})
</script>

<style lang="scss" scoped>
.button {
  width: fit-content;
  text-align: center;
  max-width: 400px;
  padding: 1.2rem;
  background: transparent;
  --notchSize: 15px;
  clip-path: 
    polygon(
      0% var(--notchSize), 
      var(--notchSize) 0%, 
      100% 0%, 
      100% var(--notchSize), 
      100% calc(100% - var(--notchSize)), 
      calc(100% - var(--notchSize)) 100%, 
      var(--notchSize) 100%, 
      0 100% 
    );
  font-size: 1.5em;
  cursor: pointer;
  &.primary {
    border: 2px solid #000;
    background-color: #fff;
    color: #000;
  }
  &.secondary {
    background-color: #000;
    color: #fff;
  }
}
</style>