<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>提交表单</span>
      <x-form :config="formConfig" style="margin-top: 10px;"></x-form>
    </div>
    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="8">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
           <x-form :config="formConfig"></x-form>
        </textarea>
      </el-col>
      <el-col :span="16">
        <span>script示例：</span>
        <textarea class="code-textarea" rows="45" readonly>
          export default {
            data() {
              return {
                formConfig: {
                  params: [
                    [
                      {type: "switch", param: "switch", label: "开关", onValue: true, offValue: false},
                      {type: "radio", param: "radio", label: "单选框", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}]},
                      {type: "checkbox", param: "checkbox", label: "多选框", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}, {label: "选项三", value: "3"}]},
                      {type: "select", param: "select", label: "选择器", placeholder: "请选择内容", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}, {label: "选项三", value: "3"}]}
                    ],
                    [
                      {type: "input", param: "input", label: "输入框", placeholder: "请输入内容"},
                      {type: "time", param: "time", label: "时间选择器", placeholder: "请选择时间", option: {start: '00:00', step: '00:10', end: '23:50'}},
                      {type: "date", param: "date", label: "日期选择器", placeholder: "请选择日期"},
                      {type: "datetime", param: "datetime", label: "日期时间选择器", placeholder: "请选择具体时间"},
                    ],
                    [
                      {type: "textarea", param: "textarea", label: "文本框", placeholder: "请输入内容"},
                      {},
                    ]
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
            [
              {type: "switch", param: "switch", label: "开关", onValue: true, offValue: false},
              {type: "radio", param: "radio", label: "单选框", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}]},
              {type: "checkbox", param: "checkbox", label: "多选框", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}, {label: "选项三", value: "3"}]},
              {type: "select", param: "select", label: "选择器", placeholder: "请选择内容", options: [{label: "选项一", value: "1"}, {label: "选项二", value: "2"}, {label: "选项三", value: "3"}]}
            ],
            [
              {type: "input", param: "input", label: "输入框", placeholder: "请输入内容"},
              {type: "time", param: "time", label: "时间选择器", placeholder: "请选择时间", option: {start: '00:00', step: '00:10', end: '23:50'}},
              {type: "date", param: "date", label: "日期选择器", placeholder: "请选择日期"},
              {type: "datetime", param: "datetime", label: "日期时间选择器", placeholder: "请选择具体时间"},
            ],
            [
              {type: "textarea", param: "textarea", label: "文本框", placeholder: "请输入内容"},
              {},
            ]
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