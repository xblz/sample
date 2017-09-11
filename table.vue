<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>列表信息</span>
      <x-table :config="tableConfig" style="margin-top: 10px;"></x-table>
    </div>

    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="8">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
           <x-table :config="tableConfig"></x-table>
        </textarea>
      </el-col>
      <el-col :span="16">
        <span>script示例：</span>
        <textarea class="code-textarea" rows="55" readonly>
        export default {
          data() {
            return {
              tableConfig: {
                params: [
                  {
                    label: "默认()",
                    prop: "name",
                  }, {
                    label: "文字(label)",
                    prop: "address",
                    type: "label"
                  }, {
                    label: "文字(带有adapter)",
                    prop: "gender",
                    adapter: {0: "男", 1: "女"}
                  }, {
                    label: "开关(switch)",
                    prop: "switch",
                    type: "switch"
                  }, {
                    label: "日期(date)",
                    prop: "date",
                    type: "date"
                  }, {
                    label: "按钮操作(button)",
                    type: "button",
                    buttons: [
                      {
                        text: "修改",
                        action: function (index, obj) {
                          alert(index + JSON.stringify(obj));
                        }
                      },
                      {
                        text: "删除",
                        action: function (index, obj) {
                          alert(index + JSON.stringify(obj));
                        }
                      }
                    ]
                  }
                ],
                data: []
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

  import {getListData} from "../../api/sampleApi"


  export default {
    methods: {
      getSampleList() {
        var self = this;
        var params = {};
        params.pageSize = 10;
        getListData(params, function (data) {
          self.tableConfig.data = data.data;
        })
      }
    },
    created: function () {
      this.getSampleList()
    },
    data() {
      return {
        tableConfig: {
          // 列表内容
          params: [
            {
              label: "默认()",
              prop: "name",
            }, {
              label: "文字(label)",
              prop: "address",
            }, {
              label: "文字(label)",
              prop: "gender",
              adapter: {0: "男", 1: "女"}
            }, {
              label: "开关(switch)",
              prop: "switch",
              type: "switch"
            }, {
              label: "日期(date)",
              prop: "date",
              type: "date"
            }, {
              label: "按钮操作(button)",
              type: "button",
              prop: "href",
              buttons: [
                {
                  text: "修改",
                  action: function (index, obj) {
                    alert(index + JSON.stringify(obj));
                  }
                },
                {
                  text: "删除",
                  action: function (index, obj) {
                    alert(index + JSON.stringify(obj));
                  }
                }
              ]

            }
          ],
          data: []
        }
      }
    }
  }

</script>