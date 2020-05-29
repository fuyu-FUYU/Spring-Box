<template>
  <div class="zk-box">
    <div class="zk-flex zk-pd">
      <div class="zk-btn" @click="alerts">提示框</div>
      <Eject type="alert" @took="okfall" :showstate="showa" @tocancel="cancelfall" >
        <span slot="tlt">提示</span>
        <div slot="text">{{msg}}</div>
      </Eject>
    </div>
    <div class="zk-flex zk-pd">
      <div class="zk-btn zk-blue" @click="confirms">对话框</div>
      <Eject type="confirm" @took="okfall2" @tocancel="cancelfall2" :showstate="showc">
        <span slot="tlt">确认</span>
        <div slot="text">{{msg}}</div>
      </Eject>
    </div>
  </div>
</template>
<script>
import Eject from "../views/eject";
export default {
  name: "demo",
  components: {
    Eject
  },
  data() {
    return {
      showa: false,
      showc: false,
      msg: ""
    };
  },
  methods: {
    alerts() {
      this.showa = true;
      this.msg = "这是一个提示的弹窗";

    },
    confirms() {
      this.showc = true;
      this.msg = "这是一个对话的弹窗";
    },
    okfall() {
      this.showa = false;
    },
    cancelfall() {
      this.showa = false;
    },
    okfall2() {
      this.showc = false;
    },
    cancelfall2() {
      this.showc = false;
    }
  }
};
</script>
<style>
.zk-box {
  display: flex;
  line-height: 0.65rem;
  font-size: 0.26rem;
  color: #333;
  padding: 4.5rem 0;
}
.zk-flex {
  flex: 1;
}
.zk-pd {
  padding: 0.5rem 0.1rem;
}
.zk-btn {
  display: block;
  line-height: 0.88rem;
  text-align: Center;
  color: #fff;
  border-radius: 0.12rem;
  background: #488bf1;
}
.zk-blue {
  background: #488bf1;
}
</style>