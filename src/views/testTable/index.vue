<template>
  <div class="app-container">
    <el-table
      v-loading="listLoading"
      :data="tableData"
      element-loading-text="Loading"
      border
      fit
      highlight-current-row
    >
      <el-table-column prop="name" label="姓名" width="150"></el-table-column>
      <el-table-column prop="date" label="出生日期" width="150"></el-table-column>
      <el-table-column prop="address" label="家庭住址"></el-table-column>

      <el-table-column prop="button" label="Button" width="380">
        <template slot-scope="{row,$index}">
          <el-button type="primary" @click="Edit(row,$index)">修改</el-button>
          <el-button type="danger" @click="delOffice(row.id)">删除</el-button>
          <el-button type="primary" @click="addOffice(row)">添加下级机构</el-button>
        </template>
        <!-- <el-button type="primary" icon="el-icon-edit" @click="Edit">修改</el-button>
        <el-button type="primary" icon="el-icon-delete">删除</el-button>
        <el-button type="primary" icon="el-icon-share">分享</el-button> -->
      </el-table-column>
    </el-table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tableData: [
        {
          date: "2020-05-01",
          name: "Tom1",
          address: "No. 181, Grove St, Los Angeles",
        },
        {
          date: "2020-05-02",
          name: "Tom2",
          address: "No. 182, Grove St, Los Angeles",
        },
        {
          date: "2020-05-03",
          name: "Tom3",
          address: "No. 183, Grove St, Los Angeles",
        },
        {
          date: "2020-05-04",
          name: "Tom4",
          address: "No. 184, Grove St, Los Angeles",
        },
        {
          date: "2020-05-05",
          name: "Tom5",
          address: "No. 185, Grove St, Los Angeles",
        },
        {
          date: "2020-05-06",
          name: "Tom6",
          address: "No. 186, Grove St, Los Angeles",
        },
        {
          date: "2020-05-07",
          name: "Tom7",
          address: "No. 187, Grove St, Los Angeles",
        },
      ],
    };
  },
  methods: {
    Edit(row) {
      this.$router.push({
        path: "/form/index",
        query: {
          row: row
        },
      });
    },
  },
};
</script>