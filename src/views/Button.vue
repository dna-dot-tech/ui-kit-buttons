<template>
<div class="btn-wrap" style="width: fit-content;">
  <button 
    :style="`padding:${height}px ${width}px;font-size:${textSize}em;background:${bg};color:${color}`">
    <slot></slot>
  </button>
</div>
</template>

<script>
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'customButton',
  props: {
    width: {
      type: Number,
      default: 20
    },
    height:{
      type: Number,
      default: 45
    },
    textSize:{
      type: Number,
      default: 1.6,
    },
    type: {
      type: String,
      default: 'default'
    },
    disabled: {
      type: Boolean,
      default: false
    },
    color: {
      type: String,
      default: '#000'
    },
    bg: {
      type: String,
      default: 'transparent'
    }
  }
})
</script>

<style lang="scss" scoped>
button {
  border: 2px solid #000;
  display: inline-block;
  position: relative;
  font-family: monospace;
  --notchSize: 14px;
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
}

.btn-wrap:before, .btn-wrap:after {
  height: 15px;
  width: 3px;
  background: rgb(69, 130, 180);
  position: absolute;
  content: '';
}

.btn-wrap:before {
  top: -2px;
  left: 4px;
  clip-path: polygon(0 30%, 100% 0, 100% 100%, 0 70%);
  transform: rotate(45deg) translate(-90%);
  animation: goUpout 0.3s ease-out;
}

.btn-wrap:after {
  bottom: -2px;
  right: 4px;  
  clip-path: polygon(0% 0%, 100% 30%, 100% 75%, 0% 100%);
  transform: rotate(45deg) translate(90%);
  animation: goDownout 0.3s ease-out;
}

.btn-wrap{
  transition: all 0.3s ease-in-out;
}

.btn-wrap:hover {
  filter: drop-shadow(1px 6px 6px rgba(50, 50, 0, 0.5));
}

.btn-wrap:hover::after{
  animation: goDownin 0.3s ease-out;
}

.btn-wrap:hover::before{
  animation: goUpin 0.3s ease-out,
}

@keyframes goDownin{
  0%{ transform: rotate(45deg) translate(-90%);}
  100%{ transform: rotate(45deg) translate(90%);}
}
@keyframes goUpin{
  0%{ transform: rotate(45deg) translate(90%);}
  100%{ transform: rotate(45deg) translate(-90%);}
}
@keyframes goDownout{
  0%{ transform: rotate(45deg) translate(90%);}
  100%{ transform: rotate(45deg) translate(-20%);}
}
@keyframes goUpout{
  0%{ transform: rotate(45deg) translate(-90%);}
  100%{ transform: rotate(45deg) translate(20%);}
}
button:before, button:after {
  height: 26px;
  width: 18px;
  background: rgb(0, 0, 0);
  position: absolute;
  content: '';
}

button:before {
  top: 0;
  left: 0;
  border-right: 2px solid #000;
  transform: rotate(45deg) translate(-90%);
}

button:after {
  bottom: 0;
  right: 0;
  border-left: 2px solid #000;
  transform: rotate(45deg) translate(90%);
}
</style>