<template>
  <div class="sl-button-group">
    <slot></slot>

  </div>
</template>

<script>
  export default {}
</script>

<style lang="scss" scoped>
  .sl-button-group {
    display: inline-flex;
    vertical-align: middle;
    > .sl-button {
      border-radius: 0;
      margin-left: -1px;
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