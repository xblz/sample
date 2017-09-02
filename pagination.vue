<template>
  <div>
    <div style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <span>分页功能</span>
      <x-pagination :config="paginationConfig" style="margin-top: 10px;"></x-pagination>
    </div>
    <el-row style="margin: 10px;padding:10px;border: 1px solid #e7ecf1">
      <el-col :span="12">
        <span>html示例：</span>
        <textarea class="code-textarea" rows="2" readonly>
         <x-pagination :config="paginationConfig"></x-pagination>
        </textarea>
      </el-col>
      <el-col :span="12">
        <span>script示例：</span>
        <textarea class="code-textarea" rows="25" readonly>
            export default {
              data() {
                return {
                  // 分页内容
                  paginationConfig: {
                    page: 1,
                    total: 100,
                    pageSize: 10,
                    pageSizes: [10, 20, 50, 100],
                    handleSizeChange(pageSize) {
                      alert(pageSize)
                    },
                    handleCurrentChange(pageNum) {
                      alert(pageNum)
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
        // 分页内容
        paginationConfig: {
          page: 1,  // 页码
          total: 100,  // 总条数
          pageSize: 10,
          pageSizes: [10, 20, 50, 100],
          handleSizeChange(pageSize) {
            alert(pageSize)
          },
          handleCurrentChange(pageNum) {
            alert(pageNum)
          }
        }
      }
    }
  }

</script>