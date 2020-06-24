<template>
  <div class="sl-button-group">
    <slot></slot>

  </div>
</template>

<script>
  export default {
  //  对子元素进行检查
    mounted() {
      for (let node of this.$el.children) {
        const name = node.nodeName.toLowerCase()
        if (name !== "button") {
          console.warn(`sl-button-group 的子元素应该全部都是 sl-button, 但是其中包含了 ${name}`)
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  .sl-button-group {
    display: inline-flex;
    vertical-align: middle;
    > .sl-button {
      border-radius: 0;
      &:not(:first-child){
        margin-left: -1px;
      }
      &:first-child {
        border-top-left-radius: var(--border-radius);
        border-bottom-left-radius: var(--border-radius);
      }
      &:last-child {
        display: inline-flex;
        border-top-right-radius: var(--border-radius);
        border-bottom-right-radius: var(--border-radius);
        .icon {
          order: 2;
        }
      }
      &:hover {
        position: relative;
        z-index: 1;
      }

    }
  }

</style>