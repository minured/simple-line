<template>
  <svg class="icon" aria-hidden="true">
    <use :xlink:href="`#icon-${iconName}`"></use>
  </svg>
</template>
<script>
export default {
  props:['iconName']
}
</script>
<style scoped>
  .icon {
    margin-right: 5px;
    width: 1.2em;
    height: 1.2em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
  }
</style>