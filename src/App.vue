<template>
  <div>
    <SLButton>仅文字</SLButton>
    <SLButton  icon-name="setting" icon-position="left">左边icon</SLButton>
    <SLButton  icon-name="setting" icon-position="right">右边icon</SLButton>
  </div>
</template>

<script>
  import SLButton from './components/SLButton'
  export default {
    name:"App",
    components:{SLButton}
  }
</script>

<style></style>
