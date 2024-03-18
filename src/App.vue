<template>
     <ClickerOne/>
</template>

<script>
import ClickerOne from './components/HelloWorld.vue'

export default {
  components: {
    ClickerOne
  }
}
</script>

<style>
*
{
  margin: 0;
  box-sizing: border-box;
  outline: none !important;
}
body
{
  background-color: #020212;
}
#app {
  width: 100%;
  height: 100vh;
  text-align: center;
  display: grid;
  place-items: center;
}
</style>
