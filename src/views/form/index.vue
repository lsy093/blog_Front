<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="100px">
      <el-form-item label="姓名">
        <!-- <span>{{this.$route.query.row.name}}</span> -->
        <el-input :value="form.name" style="width: 20%;" />
      </el-form-item>
      <el-form-item label="出生年月日">
        <el-col :span="11">
          <el-date-picker type="date" placeholder="选择日期" v-model="form.date" style="width: 44%;"></el-date-picker>
        </el-col>
      </el-form-item>
      <el-form-item label="家庭住址">
        <el-input v-model="form.address" style="width: 20%;" />
      </el-form-item>

      <el-form-item>
        <el-button type="primary" @click="onSubmit">创建</el-button>
        <el-button type="info" @click="empty">重置</el-button>
        <el-button @click="onCancel">取消</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: this.$route.query.row.name,
        date: this.$route.query.row.date,
        address: this.$route.query.row.address,
      },
    };
  },
  methods: {
    onSubmit() {
      this.$message("submit!");
      console.log(this.form.name)
      console.log(this.form.date)
      console.log(this.form.address)
      console.log(this.$route.params.name)
    },
    onCancel() {
      this.$message({
        message: "cancel!",
        type: "warning",
      });
    },
    empty() {
      this.form.name = "";
      this.form.data = this.form.placeholder;
      this.form.address = "";
    },
  },
};
</script>

<style scoped>
.line {
  text-align: center;
}
</style>

