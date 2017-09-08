<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>筛选条件</span>
      <x-search :config="searchConfig" style="margin-top: 10px;"></x-search>
    </div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>列表信息</span>
      <x-table :config="tableConfig" style="margin-top: 10px;"></x-table>
      <x-pagination :config="paginationConfig" style="margin-top: 10px;text-align: center"></x-pagination>
    </div>
  </div>
</template>


<script>

  import {getListData} from "../../api/sampleApi"
  import {confirmDialog} from "../../common/dialogUtil"

  export default {
    methods: {
      getSmsList() {
        var self = this;
        var params = {};
        params.pageSize = self.paginationConfig.pageSize;
        params.page = self.paginationConfig.page;
        getListData(params, function (data) {
          self.tableConfig.data = data.data;
          self.paginationConfig.total = data.total;
        })
      }
    },
    created: function () {
      this.getSmsList()
    },
    data() {
      const context = this;
      return {
        searchConfig: {
          // 筛选内容
          params: [
            {
              type: "input",
              param: "name",
              label: "用户名",
              placeholder: "请输入用户名"
            },
            {
              type: "input",
              param: "mobile",
              label: "手机号",
              placeholder: "请输入手机号"
            }
          ],
          // 查询按钮点击事件
          onSearch(obj) {
            console.log(JSON.stringify(obj));
            context.getSmsList();
          }
        },
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
        },
        paginationConfig: {
          page: 1,  // 页码
          total: 100,  // 总条数
          pageSize: 10,
          pageSizes: [10, 20, 50, 100],
          handleSizeChange(pageSize) {
            context.paginationConfig.pageSize = pageSize;
            context.getSmsList();
          },
          handleCurrentChange(pageNum) {
            context.paginationConfig.page = pageNum;
            context.getSmsList();
          }
        }
      }
    }
  }

</script>