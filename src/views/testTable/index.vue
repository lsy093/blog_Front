<template>
  <el-table
    :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
    style="width: 100%"
  >
    <el-table-column label="Name" prop="name"></el-table-column>
    <el-table-column label="Sex" prop="sex"></el-table-column>
    <el-table-column label="Date" prop="date"></el-table-column>
    <el-table-column label="Address" prop="address"></el-table-column>
    <el-table-column label="Phone" prop="phone"></el-table-column>
    <el-table-column align="right">
      <!-- <template slot="header" slot-scope="scope">
        <el-input v-model="search" size="mini" placeholder="输入关键字搜索" />
      </template> -->
      <template slot-scope="scope">
        <el-button size="mini" @click="handleEdit(scope.$index, scope.row)">Edit</el-button>
        <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">Delete</el-button>
      </template>
    </el-table-column>
  </el-table>
</template>
<script>
export default {
  data() {
    return {
      tableData: [
        {
          date: "2020-05-01",
          sex:"男",
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
          row: row,
        },
      });
    },
    handleEdit(index, row) {
      console.log(index, row);
      this.$router.push({ path: "/form/index", query: { row: row } });
    },
    handleDelete(index, row) {
      console.log(index, row);
    },
  },
};
</script>