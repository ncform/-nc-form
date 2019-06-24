<template>
  <div class="nc-form">
    <!-- disabled / readonly / placeholder / hidden : use the computed version, not the config version. -->
    <!-- modelVal: for binding value. -->
    <ncform :form-schema="mergeConfig.schema" :form-name="formName" v-model="modelVal"></ncform>
  </div>
</template>

<style lang="scss" scoped>
.nc-form {
  border: 1px solid #EBEEF5;
}
</style>

<script>
import ncformCommon from "@ncform/ncform-common";

export default {
  mixins: [ncformCommon.mixins.vue.controlMixin],

  i18nData: {
    // i18n
    en: {
    },
    zh_cn: {
    }
  },

  props: {
    value: Object
  },

  data() {
    return {
      formName: "tmta-widget_" + ncformCommon.ncformUtils.genRandomId(),
      formVal: {},

      defaultConfig: {
        // your config's default value ( Note: use mergeConfig to get config value )
        schema: null
      }
    };
  },

  methods: {
    // you can handle the modelVal before $emit it ( before this.$emit('input') )
    _processModelVal(modelVal) {
      return modelVal;
    }

    // you can use this.$http to make some http requests ( this.$http is the same as axios )
  }
};
</script>
