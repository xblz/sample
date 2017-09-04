<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>列表数据</span>
      <x-table :config="tableConfig" style="margin-top: 10px;"></x-table>
    </div>

    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="10">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
           <x-table :config="tableConfig"></x-table>
        </textarea>
      </el-col>
      <el-col :span="14">
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
                    label: "开关(switch)",
                    prop: "switch",
                    type: "switch"
                  }, {
                    label: "日期(date)",
                    prop: "date",
                    type: "date"
                  }, {
                    label: "链接类(href)",
                    prop: "href",
                    type: "href",
                    action(index, obj) {
                      alert(index + JSON.stringify(obj));
                    }
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

  import {httpGet} from "./../../common/httpUtil"
  import {formatDate} from "./../../common/dateUtil"

  import sampleMock from "./../../mock/sampleMock"


  export default {
    methods: {
      getListData(url, data, func) {
        httpGet(url, data, func)
      }
    },
    /* 页面加载结束监听 */
    created: function () {
      let self = this;
      this.getListData("/sample/list", {}, function (data) {
        self.tableConfig.data = data.data;
      })
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
              type: "label"
            }, {
              label: "开关(switch)",
              prop: "switch",
              type: "switch"
            }, {
              label: "日期(date)",
              prop: "date",
              type: "date"
            }, {
              label: "链接类(href)",
              prop: "href",
              type: "href",
              action(index, obj) {
                alert(index + JSON.stringify(obj));
              }
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

</script>