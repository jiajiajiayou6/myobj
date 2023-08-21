<template>
  <div class="hello">
    <el-container>
      <el-header>
        <h1>{{ msg }}</h1>
      </el-header>
    </el-container>
    <div class="content">
      <el-descriptions v-for="item in column" :key="item.id">
        <el-descriptions-item label="用户名">{{ item.username }}</el-descriptions-item>
        <el-descriptions-item label="手机号">{{ item.phone }}</el-descriptions-item>
        <el-descriptions-item label="居住地">{{ item.residence }}</el-descriptions-item>
        <el-descriptions-item label="备注">
          <el-tag size="small">{{ item.remarks }}</el-tag>
        </el-descriptions-item>
        <el-descriptions-item label="联系地址">{{ item.address }}</el-descriptions-item>
        <el-descriptions-item label="详细">
          <el-tag @click="drawer = true,shiju(item)" type="primary" style="margin-left: 16px;">点我打开</el-tag>
        </el-descriptions-item>
      </el-descriptions>
    </div>
    <el-drawer title="详细信息" :visible.sync="drawer" size="50%">
      <div v-for="item in kong.detail" :key="item.indexs">
        编号:
        <input class="duo" type="text" v-model="item.indexs" name id />
        <br />介绍:
        <input class="duo" type="text" v-model="item.sssss" name id />
        <br />
      </div>
    </el-drawer>
  </div>
</template>
<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      drawer: false,
      innerDrawer: false,
      column: [
        {
          id: 1, //id
          username: "小明", //用户名
          phone: "111111111111", //手机号
          residence: "上海", //居住地
          remarks: "学校", //备注
          address: "江苏省苏州市吴中区吴中大道 1188 号", //联系地址
          detail: [{ indexs: 1, sssss: "aqwedrf" }] //详细
        },
        {
          id: 2, //id
          username: "小王", //用户名
          phone: "22222222222", //手机号
          residence: "上海", //居住地
          remarks: "学校", //备注
          address: "江苏省苏州市吴中区吴中大道 1188 号", //联系地址
          detail: [{ indexs: 2, sssss: "222" }] //详细
        },
        {
          id: 3, //id
          username: "小风", //用户名
          phone: "33333333333", //手机号
          residence: "上海", //居住地
          remarks: "学校", //备注
          address: "江苏省苏州市吴中区吴中大道 1188 号", //联系地址
          detail: [{ indexs: 3, sssss: "333" }] //详细
        },
        {
          id: 4, //id
          username: "小六", //用户名
          phone: "44444444444", //手机号
          residence: "上海", //居住地
          remarks: "学校", //备注
          address: "江苏省苏州市吴中区吴中大道 1188 号", //联系地址
          detail: [{ indexs: 4, sssss: "444" }] //详细
        }
      ],
      kong: []
    };
  },
  methods: {
    shiju(item) {
      console.log(item.detail);
      this.kong = item;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
.el-header {
  // background-color: #b3c0d1;
  color: #333;
  text-align: center;
  height: 60px;
  line-height: 60px;
}
.content {
  width: 80%;
  height: 80%;
  margin: auto;
  border: 3px solid rgb(227, 227, 227);
  border-radius: 8px;
  margin-top: 20px;
}
.el-descriptions {
  border-bottom: 3px solid rgb(227, 227, 227);
  padding-top: 8px;
  padding-left: 8px;
}
.duo {
  border: none !important;
}
</style>
