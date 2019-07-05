<template>
  <div class="drawer">
    <div :class="['mask',visible?'':'isShowMask']" @click.self="cancelMask">

      <div :class="['drawer',visible?'isShowDrawer':'']">

        <div class="wrap">
          <slot></slot>
        </div>

      </div>

    </div>

  </div>
</template>

<script>
export default {
  props: {
    visible: {
      type: Boolean,
      default: false
    }
  },

  methods: {
    cancelMask() {
      if (this.visible) {
        this.$emit("before-close");
        this.$emit("update:visible", !this.visible);
      }
    }
  }
};
</script>

<style lang='scss'>
.drawer {
  .mask {
    border: 1px solid #000;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(218, 218, 218, 0.884);
    overflow: auto;
    outline: 0;
    z-index: 10;
    overflow: hidden;
  }

  .wrap {
    overflow: auto;
    height: 100vw;
  }

  .drawer {
    border: 1px solid #000;
    background-color: #fff;
    height: 100%;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    background-color: #fff;
    border: 0;
    background-clip: padding-box;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    transform: translateX(100%);
    opacity: 1;
    visibility: visible;
    transition: all 0.5s;
  }

  .isShowDrawer {
    transform: translateX(0);
  }

  .isShowMask {
    opacity: 0;
    visibility: hidden;
    transition: 0.5s;
  }
}
</style>
