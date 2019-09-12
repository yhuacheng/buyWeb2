<template>
  <div class="fbox">
    <div class="welcome">
      欢迎登录！刘德华，您当前账户余额： ￥ <span class="userMoney">18880.00</span>
      <el-button type="success" size="small" class="ml20" @click='recharge'>充值</el-button>
      <el-button type="danger" size="small" class="ml20" @click="cashMoney">提现</el-button>
      <span class="ml50">
      自注册以来，您共进行了 <span class="tasknum">112</span> 个任务，其中已完成 <span class="tasknum">100</span> 个，进行中 <span class="tasknum">10</span> 个，异常 <span class="tasknum">2</span> 个
      </span>
    </div>

    <div class="list-title"><i class="el-icon-s-grid"></i> 产品列表</div>

    <div class="product-box">
      <div class="product">
        <p class="name">亚马逊FBA任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="fbaTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">亚马逊加购任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="buyCarTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">亚马逊心愿任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="wishTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">亚马逊点赞任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="likesTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">亚马逊QA任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="QaTask">创建任务</el-button></p>
      </div>
    </div>

    <div class="product-box">
      <div class="product">
        <p class="name">速卖通FBA任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="fbaTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">速卖通加购任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="buyCarTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">速卖通心愿任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="wishTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">速卖通点赞任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="likesTask">创建任务</el-button></p>
      </div>
      <div class="product">
        <p class="name">速卖通QA任务</p>
        <p class="des">亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务亚马逊FBA任务</p>
        <p class="price">￥100 起</p>
        <p class="btn"><el-button type="info" size="small" @click="QaTask">创建任务</el-button></p>
      </div>
    </div>
    <!--提示-->
    <div class="errTip">
      <el-dialog title="提示" :visible.sync="errorModel" width="30%" center>
        <span>您有<span class="fz16 redRequired">{{errorNum}}</span>条异常信息，请前往处理！</span>
        <span slot="footer" class="dialog-footer">
          <el-button type="primary" @click="toErrorList">确 定</el-button>
        </span>
      </el-dialog>
    </div>
    <!--充值-->
    <el-dialog title='充值' :visible.sync='RechargeModal' :close-on-click-modal='false' width="30%">
      <el-form :model='rechargeForm' ref='rechargeForm' class="form-item" :rules='rechargeRules' :inline="true"
        label-width="80px">
        <el-row>
          <el-col>
            <el-form-item label='充值金额'>
              <el-radio-group v-model="rechargeForm.money">
                <el-radio-button label="100元"></el-radio-button>
                <el-radio-button label="300元"></el-radio-button>
                <el-radio-button label="500元"></el-radio-button>
                <el-radio-button label="800元"></el-radio-button>
                <el-radio-button label="1000元"></el-radio-button>
              </el-radio-group>
            </el-form-item>
          </el-col>
        </el-row>
        <el-row>
          <el-col>
            <el-form-item label='自定义' prop='moneys'>
              <el-input v-model='rechargeForm.moneys' class='disInline'></el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-form-item label='付款方式'>
          <el-radio-group v-model="rechargeForm.payType">
            <el-radio :label="1">支付宝</el-radio>
            <el-radio :label="2">微信</el-radio>
            <el-radio :label="3">银行卡</el-radio>
          </el-radio-group>
        </el-form-item>
      </el-form>
      <div slot='footer' class="dialog-footer">
        <el-button type='info'>确认</el-button>
        <el-button @click='RechargeModal=false'>取消</el-button>
      </div>
    </el-dialog>
  </div>
</template>

<script>
  import bus from '../common/bus'
  import vali from '../common/validate'
  export default {
    name: 'loginHome',
    data() {
      return {
        item: '1',
        RechargeModal: false, //充值
        errorModel: false,
        collapse: false,
        errorNum: '0',
        name: sessionStorage.getItem('userName'),
        times: sessionStorage.getItem('times'),
        rechargeForm: {
          money: '',
          moneys: '',
          payType: ''
        },
        rechargeRules: {
          moneys: [{
              validator: vali.proPrice,
              trigger: 'change'
            },
            {
              required: false,
              trigger: 'change'
            }
          ]
        }
      }
    },
    created() {
      bus.$on('collapse', msg => {
        this.collapse = msg
      })
      // this.getSrc()
      this.isError()
    },
    computed: {
      role() {
        return this.name === 'admin' ? '超级管理员' : '普通用户'
      }
    },
    mounted() {
    },
    methods: {
      //充值
      recharge() {
        let _this = this
        _this.RechargeModal = true
      },
      isError() {
        let _this = this
        let err = _this.errorNum
        if (err > 0) {
          _this.errorModel = true
        }
      },
      // 前往异常订单
      toErrorList() {
        this.$router.push({
          name: 'taskManage',
          params: {
            active: 7
          }
        })
      },
      // 更多任务
      moreTask() {
        let _this = this
        let status = true
        _this.$router.push({
          name: "taskManage",
          params: {
            taskTypeModel: true
          }
        })
      },
      // FBA任务
      fbaTask() {
        let _this = this
        _this.$router.push('/FbaTask')
      },
      // 心愿任务
      wishTask() {
        let _this = this
        _this.$router.push({
          name: 'wishTask'
        })
      },
      //购物车任务
      buyCarTask() {
        let _this = this
        _this.$router.push('/buyCarTask')
      },
      //点赞任务
      likesTask() {
        let _this = this
        _this.$router.push('/likesTask')
      },
      //QA任务
      QaTask() {
        let _this = this
        _this.$router.push('/QaTask')
      },
      // 提现
      cashMoney() {
        this.$router.push('/CashWithdrawal')
      },
      getSrc() {
        let _this = this
        if (_this.name === 'admin') {
          _this.hashBd = true
        } else {
          _this.hashBd = false
        }
      }
    }
  }
</script>

<style scoped>
  .el-row {
    margin-bottom: 20px;
  }

  .todo-item {
    font-size: 14px;
  }

  .todo-item-del {
    text-decoration: line-through;
    color: #999;
  }

  .isRed {
    display: inline-block;
    height: 100px;
    width: 100%;
    color: red;
  }
</style>
