<template>
  <div class="fbox">
    <div class="mb20 tabsTxt">
      <span>任务管理</span>
      <span>/</span>
      <span>任务详情</span>
    </div>
    <el-form class="demo-item" label-width="130px">
      <div class="modalTitle mb20 fz16">订单信息</div>
      <el-row>
        <el-col :span='8' :xs='24'>
          <el-form-item label="任务编码：">
            <span>20190611173647296133_6</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="平台/国家：">
            <span>亚马逊</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="任务状态：">
            <span>订单异常</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="任务类型：">
            <span>不留评</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="店铺名称：">
            <span>toto</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品名称：">
            <span>手机架</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品图片：">
            <img src="https://images-na.ssl-images-amazon.com/images/G/01/AmazonExports/Fuji/2019/July/cel_260._SY260_CB442727991_.jpg" class="eval_img">
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="品牌：">
            <span>AMALI</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品类型：">
            <span>3C电子</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品ASIN：">
            <span>57564646</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品价格：">
            <span>$ 12.00</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="购买数量：">
            <span>10</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="关键词：">
            <span>Hands-Free Car Cell Phone Holder</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品链接：">
            <span><a href="https://www.amazon.com">https://www.amazon.com</a></span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="关键字类型：">
            <span>产品关键字</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="任务执行时间：">
            <span>2019-09-09</span>
          </el-form-item>
        </el-col>
      </el-row>

      <div class="modalTitle mb20 fz16">购买信息</div>

      <el-row>
        <el-col :span='8' :xs='24'>
          <el-form-item label="购买时间：">
            <span>2019-09-09</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="Amazon订单号：">
            <span>456416313</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品金额：">
            <span>$ 25.36</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品运费：">
            <span>$ 2.36</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="产品税费：">
            <span>$ 0.36</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="其他费用：">
            <span>$ 0.00</span>
          </el-form-item>
        </el-col>
        <el-col :span='8' :xs='24'>
          <el-form-item label="实际支付：">
            <span>$ 28.08</span>
          </el-form-item>
        </el-col>
      </el-row>

    </el-form>
    <el-button class="mt30" size="medium" @click="backBtn">返回</el-button>
  </div>
</template>

<script>
  export default {
    name: 'viewTaskDetails',
    data() {
      return {
        form: {}
      }
    },
    methods: {
      backBtn() {
        this.$router.push('/taskManage')
      }
    }
  }
</script>

<style scoped>
  .mt30 {
    margin-top: 30px;
  }

  .mt20 {
    margin-top: 20px;
  }

  .mb20 {
    margin-bottom: 20px;
    font-size: 14px;
  }

  .contentView {
    text-align: left;
    margin: 0 auto 50px;
    position: relative;
  }

  .detailbox1 li {
    width: 48%;
    float: left;
    list-style: none;
    line-height: 36px;
    margin-bottom: 8px;
    overflow: hidden;
  }

  .detailbox1 li p {
    margin: 0;
    display: inline-block;
    color: #666;
  }

  .detailbox1 li p img {
    display: inline-block;
  }

  .detailbox {
    overflow: hidden;
    margin-top: 20px;
    font-size: 14px;
  }

  .eval_img {
    width: 60px;
    height: 60px;
    border-radius: 4px;
    cursor: pointer;
    border: 1px solid #ccc;
    margin-right: 10px;
  }

  .detailbox1 {
    padding: 0;
    margin: 0 0 0 10px;
    text-align: left;
  }

  @media screen and (max-width: 970px) {
    .detailbox1 li {
      width: 100%;
    }
  }
</style>
