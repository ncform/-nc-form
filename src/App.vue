<template>
  <div>
    <ncform
      :form-schema="formSchema"
      form-name="your-form-name"
      v-model="formSchema.value"
      @submit="submit()"
    ></ncform>
    <hr />
    <el-button @click="submit()">Submit</el-button>
  </div>
</template>

<script>
import NcForm from "./components";

export default {
  created() {
    this.$ncformAddWidget({ name: "nc-form", widget: NcForm });
  },
  data() {
    return {
      formSchema: {
        type: "object",
        properties: {
          demo: {
            type: "object",
            value: {
              name: 'daniel'
            },
            ui: {
              widget: "nc-form",
              widgetConfig: {
                schema: {
                  type: 'object',
                  properties: {
                    name: {
                      type: 'string'
                    }
                  }
                }
              }
            },
          }
        },
        ui: {
          widgetConfig: {
            layout: 'h'
          }
        },
        value: {}
      }
    };
  },
  methods: {
    submit() {
      this.$ncformValidate("your-form-name").then(data => {
        if (data.result) {
          console.log(this.$data.formSchema.value);
        }
      });
    }
  }
};
</script>
