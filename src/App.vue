<template>
  <div>
    <sl-button>仅文字</sl-button>
    <sl-button  icon-name="setting" icon-position="left">左边icon</sl-button>
    <sl-button  icon-name="setting" icon-position="right">右边icon</sl-button>
    <sl-icon icon-name="download"></sl-icon>
  </div>
</template>

<script>
  import slButton from './components/slButton'
  import slIcon from './components/sl-icon'
  export default {
    name:"App",
    components:{slButton, slIcon}
  }
</script>

<style></style>
