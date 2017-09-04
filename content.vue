<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>内容显示</span>
      <x-content :config="contentConfig" style="margin-top: 10px;"></x-content>
    </div>
    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="10">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
          <x-content :config="contentConfig"></x-content>
        </textarea>
      </el-col>
      <el-col :span="14">
        <span>script示例：</span>
        <textarea class="code-textarea" rows="30" readonly>
          export default {
            data() {
              return {
                contentConfig: {
                  params: [
                    [{param: "col1", label: "一列",}],
                    [{param: "col2", label: "二列",}, {param: "col2", label: "二列",}],
                    [{param: "col3", label: "三列",}, {param: "col3", label: "三列",}, {param: "col3", label: "三列",}],
                    [{param: "col4", label: "四列",}, {param: "col4", label: "四列",}, {param: "col4", label: "四列",}, {param: "col4", label: "四列",}],
                    [{param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}],
                  ],
                  data: {
                    col1: "一行显示一列数据",
                    col2: "一行显示二列数据",
                    col3: "一行显示三列数据",
                    col4: "一行显示四列数据",
                    col6: "一行显示六列数据",
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
        contentConfig: {
          params: [
            [{param: "col1", label: "一列",}],
            [{param: "col2", label: "二列",}, {param: "col2", label: "二列",}],
            [{param: "col3", label: "三列",}, {param: "col3", label: "三列",}, {param: "col3", label: "三列",}],
            [{param: "col4", label: "四列",}, {param: "col4", label: "四列",}, {param: "col4", label: "四列",}, {param: "col4", label: "四列",}],
            [{param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}, {param: "col6", label: "六列",}],
          ],
          data: {
            col1: "一行显示一列数据",
            col2: "一行显示二列数据",
            col3: "一行显示三列数据",
            col4: "一行显示四列数据",
            col6: "一行显示六列数据",
          }
        }
      }
    }
  }

</script>