<template>
  <!-- 变量用[]包起来 -->
  <button class="sl-button"
          :class="{[`icon-${iconPosition}`]: true}"
          @click="$emit('click')"
  >
    <sl-icon icon-name="loading" class="loading" v-if="loading"></sl-icon>
    <sl-icon v-if="iconName && !loading" :icon-name="iconName"></sl-icon>
    <slot></slot>
  </button>
</template>

<script>
  import SlIcon from './sl-icon'
  export default {
    name: 'SLButton',
    components: {SlIcon},
    // props: ['iconName', 'iconPosition']
  //  设置props的属性
    props: {
      iconName: {},
      iconPosition: {
        type: String,
        default: "left",
        //属性检查器
        validator(value) {
        //  value就是用户传的值
          return !(value !== 'left' && value !== 'right');
        }
      },
      loading: {
        type: Boolean,
        default: false,
      }
    }
  }
</script>
<style lang="scss" scoped>
  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  .sl-button {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    font-size: var(--font-size);
    height: var(--button-height);
    /*不用写宽度,用字体撑开*/
    padding: 0 1em;
    border-radius: var(--border-radius);
    border: 1px solid var(--border-color);
    background: var(--button-bg);
    margin-bottom: 5px;
    vertical-align: middle;

    &:hover {
      border-color: var(--border-color-hover);
      box-shadow: 0 0 3px rgba(0, 0, 0, 0.25);
    }
    &:active {
      background: var(--button-active-bg);
    }
    &:focus {
      outline: none;
    }
    &.icon-right {
      > .icon {
        order: 2;
        margin-right: 0;
        margin-left: 5px;
      }
    }
    .loading {
      animation: spin 1.5s infinite linear;
    }
  }

</style>