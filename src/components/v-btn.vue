<template>
  <div class="v-btn" :click="click" :class="[className, 'v-btn__' + colorBg]">
    <i class="material-icons" v-if="btnIcon">
      {{ btnIcon }}
    </i>
    <span v-else>{{ title }}</span>
  </div>
</template>

<script>
export default {
  name: "v-btn",
  props: {
    title: {
      type: String,
      default: "Отправить",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    btnIcon: {
      type: String,
      default: "",
    },
    small: {
      type: Boolean,
      default: false,
    },
    colorBg: {
        type: String,
        default: 'default'
    }
  },
  data() {
    return {
        
    };
  },
  computed: {
    className() {
      return {
        "v-btn__disabled": this.disabled,
        "v-btn__icon": this.btnIcon,
        "v-btn__small": this.small,
        colorBg : this.colorBg
      };
    }
  },
  methods: {
    click() {
      this.$emit("click");
    },
  },
};
</script>

<style lang="scss">
.v-btn {
  border-radius: 20px;
  padding: 12px 24px;
  color: #fff;
  background-color: #000;
  font-size: 24px;
  font-weight: 700;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 8px;
  &__primary {
    background-color: blue;
  }
  &__secondary {
    background-color: darkcyan;
  }
  &:hover {
    opacity: 0.7;
  }
  &__disabled {
    pointer-events: none;
  }
  &__icon {
    padding: 12px;
  }
  &__small {
    border-radius: 16px;
    padding: 10px 18px;
    font-size: 18px;
    &.v-btn__icon {
        padding: 10px;
    }
  }
}
</style>
