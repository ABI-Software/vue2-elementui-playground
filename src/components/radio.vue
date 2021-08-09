<template>
  <el-radio
    :label="label"
    :disabled="disabled"
    v-model="current"
  >
    {{ display }}
  </el-radio>
</template>

<script>
/* eslint-disable no-alert, no-console */
import Vue from "vue";
import {
  Radio
} from "element-ui";
import lang from "element-ui/lib/locale/lang/en";
import locale from "element-ui/lib/locale";
locale.use(lang);
Vue.use(Radio);

export default {
  name: 'TestRadio',

  props: {
    value: {
      type: [String, Number, Boolean],
      required: true
    },
    label: {
      type: [String, Number, Boolean],
      required: true
    },
    disabled: {
      type: Boolean,
      default: false
    },
    display: {
      type: [String, Number],
      required: true
    }
  },

  computed: {
    current: {
      get: function() {
        return this.value
      },
      set: function(val) {
        this.$emit('input', val)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
::v-deep .el-radio__input {
  &.is-disabled {
    &.is-checked {
      .el-radio__inner {
        background-color: #909399;
        &::after {
          background-color: white;
          opacity: 80%;
        }
      }
    }
  }
}

.el-radio {
  margin-left: 0;
  padding-top: 5px;
  &:first-child {
    padding-top: 0;
  }
}

</style>