<template>
  <div>
    <sl-button :loading="loading1"
               @click="loading1=!loading1"
    >仅文字</sl-button>
    <sl-button icon-name="setting"
               icon-position="left"
               :loading="loading2"
               @click="loading2=!loading2"
    >左边icon</sl-button>
    <sl-button icon-name="setting"
               icon-position="right"
               :loading="loading3"
               @click="loading3=!loading3"
    >右边icon</sl-button>
  </div>
</template>

<script>
  import slButton from './components/slButton'
  import slIcon from './components/sl-icon'
  export default {
    data() {
      return {
        loading1: false,
        loading2: false,
        loading3: false
      }
    },
    name:"App",
    components:{slButton, slIcon}
  }
</script>

<style></style>
