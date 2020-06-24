<template>
  <!-- 变量用[]包起来 -->
  <button class="sl-button" :class="{[`icon-${iconPosition}`]: true}">
    <svg class="icon" aria-hidden="true" v-if="iconName">
      <use :xlink:href="`#icon-${iconName}`"></use>
    </svg>
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'SLButton',
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
      }
    }
  }
</script>
<style lang="scss" scoped>

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
  }

</style>