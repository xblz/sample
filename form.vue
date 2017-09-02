<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>提交表单</span>
      <x-form :config="formConfig" style="margin-top: 10px;"></x-form>
    </div>
    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="12">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
           <x-form :config="formConfig"></x-form>
        </textarea>
      </el-col>
      <el-col :span="12">
        <span>script示例：</span>
        <textarea class="code-textarea" rows="45" readonly>
          export default {
            data() {
              return {
                formConfig: {
                  params: [
                    {
                      type: "input",
                      param: "name",
                      label: "姓名",
                      defValue: "",
                      placeholder: "请输入姓名"
                    }, {
                      type: "date",
                      param: "date",
                      label: "日期",
                      defValue: "",
                      placeholder: "请选择日期"
                    }, {
                      type: "select",
                      param: "gender",
                      label: "性别",
                      defValue: "",
                      placeholder: "请选择性别",
                      options: [{label: "男", value: "1"}, {label: "女", value: "0"}],
                    }
                  ],
                  data: {},
                  //
                  onSubmit(obj) {
                    alert(JSON.stringify(obj))
                  },
                  //
                  onCancel() {
                    alert("取消")
                  }
                }
              }
            }
          }
        </textarea>
      </el-col>
    </el-row>
  </div>
</template>


<script>

  export default {
    data() {
      return {
        formConfig: {
          params: [
            {
              type: "input",
              param: "name",
              label: "姓名",
              defValue: "",
              placeholder: "请输入姓名"
            }, {
              type: "date",
              param: "date",
              label: "日期",
              defValue: "",
              placeholder: "请选择日期"
            }, {
              type: "select",
              param: "gender",
              label: "性别",
              defValue: "",
              placeholder: "请选择性别",
              options: [{label: "男", value: "1"}, {label: "女", value: "0"}],
            }
          ],
          data: {},
          //
          onSubmit(obj) {
            alert(JSON.stringify(obj))
          },
          //
          onCancel() {
            alert("取消")
          }
        }
      }
    }
  }

</script>