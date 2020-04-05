<template>
  <div class="nva-home">
    <div class="nva-head">
      <div id="u0" class="head-default">
        <img :src="LineLogo" class="line-logo">
      </div>
      <div id="u1" class="head-default">
        <img :src="ThinkBreakLogo" class="thinkBreak-logo">
      </div>
      <div id="u2" class="head-default">
        <a href="javascript:void(0);" class="button">主页</a>
      </div>
      <div id="u3" class="head-default">
        <a href="javascript:void(0);" class="button">分享</a>
      </div>
      <div id="u4" class="head-default">
        <a href="javascript:void(0);" class="button">竞技场</a>
      </div>
      <div id="u5" class="head-default">
        <a href="javascript:void(0);" class="button">登录</a>
      </div>
      <div id="u6"> {{ nowTime }}&emsp;{{ week }}</div>
    </div>
    <div class="nva-body">
      <div id="u7">
        <hr class="hr-class">
        <div id="u8" class="dynamic-title">
          <div id="u8_text">俱乐部动态</div>
        </div>
      </div>
      <div id="u9">
        <img :src="cultivateTianjin" class="cultivateTianjin">
      </div>
      <div id="u10"> sdfsdfsdf </div>
      <div id="u11">
        <hr class="hr-class">
        <div id="u12" class="dynamic-title">
          <div id="u12_text">全方位成长</div>
        </div>
        <div id="u13">
          <img :src="targetIdeal" class="targetIdeal">
        </div>
      </div>
      <div id="u14">
        <hr class="hr-class">
        <div id="u15" class="dynamic-title">
          <div id="u15_text">课程设置</div>
        </div>
        <div id="u15_detail">
          <p>由国际知名教育组织、教研专家组成的教研团队历时3年筹备适合中国本土又直接与世界接轨的少儿编程课程
            全方位、多层次调研、磨课、评价。课程不断更新，案例最贴近实际生产、生活，使学员能够真正知其所得、学有所用</p>
        </div>
        <div id="u16">
          <img :src="classLevel" class="targetIdeal">
        </div>
      </div>
      <div id="u17">
        <hr class="hr-class">
        <div id="u18" class="dynamic-title">
          <div id="u18_text">俱乐部介绍</div>
        </div>
        <div id="u18_detail">
          <p>程心程异编程俱乐部致力于推广少儿编程教育，让小朋友们从小树立正确的科技观，掌握科技工具，学会用编程思维去思考，不断突破自我，创造未来。</p>
        </div>
        <div id="u19">
          <img :src="reception" class="reception">
          <img :src="classroom" class="classroom">
        </div>
      </div>
      <div id="u20">
        <hr class="hr-class">
        <div id="u21" class="dynamic-title">
          <div id="u21_text">联系我们</div>
        </div>
        <div id="u22">
          <div class="contacts">
            <p>联系人：张老师 </p>
            <p>电话：15130308929 </p>
            <p>地址：河北省涿州市开发区火炬北街5号（程心程异少儿编程俱乐部）</p>
          </div>
          <div class="officialAccount">
            <img :src="officialAccount" class="contactsImage">
            <p>关注公众号</p>
          </div>
          <div class="customerService">
            <img :src="customerService" class="contactsImage">
            <p>微信客服号</p>
          </div>
          <div class="tiktok">
            <img :src="tiktok" class="contactsImage">
            <p>关注抖音号</p>
          </div>
        </div>
        <div id="u23">
          <div id="u23_text">用心思考 不断突破</div>
          <div id="u24_text">THINK AND BREAK</div>
        </div>
      </div>

    </div>
  </div>
</template>
<script>
import LineLogo from '@/assets/images/line-up-logo-nb.png'
import ThinkBreakLogo from '@/assets/images/think-break-logo-nb.png'
import cultivateTianjin from '@/assets/images/cultivate-tianjin.png'
import targetIdeal from '@/assets/images/target-ideal-nb.png'
import classLevel from '@/assets/images/class-levle-nb.png'
import reception from '@/assets/images/reception.png'
import classroom from '@/assets/images/classroom.png'
import officialAccount from '@/assets/images/official-account-nb.png'
import customerService from '@/assets/images/customer-service-wechat.png'
import tiktok from '@/assets/images/tiktok.png'

export default {
  data() {
    return {
      LineLogo: LineLogo,
      ThinkBreakLogo: ThinkBreakLogo,
      cultivateTianjin: cultivateTianjin,
      targetIdeal: targetIdeal,
      classLevel: classLevel,
      reception: reception,
      classroom: classroom,
      officialAccount: officialAccount,
      customerService: customerService,
      tiktok: tiktok,
      nowTime: ''
    }
  },
  mounted() {
    const _this = this
    this.timer = setInterval(() => {
      _this.timeFormate(new Date())
    }, 1000)
  },
  beforeDestroy() {
    if (this.timer) {
      clearInterval(this.timer)
    }
  },
  methods: {
    handleSelect(key, keyPath) {
      this.activeIndex = key
      console.log(key, keyPath)
    },
    timeFormate(timeStamp) {
      const year = new Date(timeStamp).getFullYear()
      const month = new Date(timeStamp).getMonth() + 1 < 10 ? '0' + (new Date(timeStamp).getMonth() + 1) : new Date(timeStamp).getMonth() + 1
      const date = new Date(timeStamp).getDate() < 10 ? '0' + new Date(timeStamp).getDate() : new Date(timeStamp).getDate()
      const hh = new Date(timeStamp).getHours() < 10 ? '0' + new Date(timeStamp).getHours() : new Date(timeStamp).getHours()
      const mm = new Date(timeStamp).getMinutes() < 10 ? '0' + new Date(timeStamp).getMinutes() : new Date(timeStamp).getMinutes()
      const ss = new Date(timeStamp).getSeconds() < 10 ? '0' + new Date(timeStamp).getSeconds() : new Date(timeStamp).getSeconds()
      this.nowTime = year + '年' + month + '月' + date + '日' + ' ' + hh + ':' + mm + ':' + ss
      const dateday = new Date(timeStamp)
      if (dateday.getDay() === 0) {
        this.week = '星期天'
      } else if (dateday.getDay() === 1) {
        this.week = '星期一'
      } else if (dateday.getDay() === 2) {
        this.week = '星期二'
      } else if (dateday.getDay() === 3) {
        this.week = '星期三'
      } else if (dateday.getDay() === 4) {
        this.week = '星期四'
      } else if (dateday.getDay() === 5) {
        this.week = '星期五'
      } else if (dateday.getDay() === 6) {
        this.week = '星期六'
      }
    }
  }
}

</script>

<style lang="scss" scoped>

#u0 {
    border-width: 0px;
    position: absolute;
    left: 189px;
    top: 45px;
    width: 160px;
    height: 46px;
    display: flex;
}

.line-logo {
    border-width: 0px;
    position: absolute;
    left: 0px;
    top: 0px;
    width: 170px;
    height: 56px;
}

#u1 {
    border-width: 0px;
    position: absolute;
    left: 369px;
    top: 41px;
    width: 160px;
    height: 24px;
    display: flex;
}

.thinkBreak-logo {
    border-width: 0px;
    position: absolute;
    left: 0px;
    top: 0px;
    width: 280px;
    height: 64px;
}

#u2 {
    border-width: 0px;
    position: absolute;
    left: 768px;
    top: 61px;
    width: 110px;
    height: 36px;
    display: flex;
}

#u3 {
    border-width: 0px;
    position: absolute;
    left: 910px;
    top: 61px;
    width: 110px;
    height: 36px;
    display: flex;
}

#u4 {
    border-width: 0px;
    position: absolute;
    left: 1052px;
    top: 61px;
    width: 110px;
    height: 36px;
    display: flex;
}

#u5 {
    border-width: 0px;
    position: absolute;
    left: 1194px;
    top: 61px;
    width: 110px;
    height: 36px;
    display: flex;
}

#u6 {
    border-width: 0px;
    position: absolute;
    left: 1060px;
    top: 33px;
    width: 250px;
    height: 30px;
    display: flex;
}

#u7 {
  width: 100%;
  position: absolute;
  top: 35px;
}

#u8 {
  border-width: 0px;
  position: absolute;
  left: 45.5%;
  top: 45px;
  width: 135px;
  height: 30px;
  border-radius:5px;
}

#u9 {
  position: absolute;
  left: 22%;
  top: 155px;
}

#u10 {
  position: absolute;
  top: 157px;
  left: 61%;
  width: 296px;
  height: 296px;
  background-color: #f9fdfac4;
}

#u11 {
  position: absolute;
  top: 490px;
  width: 100%;
  height: 350px;
}

#u12 {
  border-width: 0px;
  position: absolute;
  left: 45.5%;
  top: 45px;
  width: 135px;
  height: 30px;
  border-radius:5px;
}

#u13 {
  position: absolute;
  top: 80px;
  left: 18%;
}

#u14 {
  position: absolute;
  top: 1000px;
  width: 100%;
  height: 350px;
}
#u15 {
  border-width: 0px;
  position: absolute;
  left: 45.5%;
  top: 45px;
  width: 135px;
  height: 30px;
  border-radius:5px;
}
#u15_detail {
  position: absolute;
  top: 85px;
  left: 19%;
  width: 900px;
}

#u16 {
  position: absolute;
  top: 140px;
  left: 18%;
}

#u17 {
  position: absolute;
  top: 1570px;
  width: 100%;
  height: 350px;
}

#u18 {
  border-width: 0px;
  position: absolute;
  left: 45.5%;
  top: 45px;
  width: 135px;
  height: 30px;
  border-radius:5px;
}

#u18_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 20%;
}

#u18_detail {
  position: absolute;
  top: 85px;
  left: 19%;
  width: 900px;
}

#u19 {
  position: absolute;
  top: 170px;
  left: 18%;
}

#u20 {
  position: absolute;
  top: 2300px;
  width: 100%;
  height: 350px;
}

#u21 {
  border-width: 0px;
  position: absolute;
  left: 45.5%;
  top: 45px;
  width: 135px;
  height: 30px;
  border-radius:5px;
}

#u21_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 26%;
}

#u22 {
  position: absolute;
  top: 140px;
  left: 18%;
}

#u23 {
  border-width: 0px;
  position: absolute;
  left: 42.5%;
  top: 420px;
  width: 200px;
  height: 30px;
  border-radius:5px;
}

#u23_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 20%;
}

#u24_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 35px;
  left: 17.5%;
}

.contacts {
   position: absolute;
   top: 25px;
   width: 250px;
}

.officialAccount {
  position: absolute;
  text-align: center;
  left: 265px;
  width: 250px;
}

.customerService {
  position: absolute;
  text-align: center;
  left: 530px;
  width: 250px;
}

.tiktok {
  position: absolute;
  text-align: center;
  left: 795px;
  width: 250px;
}
.dynamic-title {
  font-family: 'ArialMT', 'Arial', sans-serif;
  letter-spacing: normal;
  background-color: #95d1d3;
  line-height: normal;
  text-transform: none;
}

#u8_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 23%;
}

#u12_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 20%;
}

#u15_text {
  position: absolute;
  text-align: center;
  font-weight: 400;
  font-style: normal;
  font-size: 17px;
  top: 4px;
  left: 26%;
}

.cultivateTianjin {
  position: absolute;
  left: 25%;
  width: 560px;
  height: 300px;
}

.targetIdeal {
  width: 1000px;
  height: 400px;
}

.reception {
  width: 600px;
  height: 350px;
}
.classroom {
  position: absolute;
  top: 150px;
  left: 390px;
  width: 600px;
  height: 350px;
}

.contactsImage {
  width: 150px;
  height: 150px;
}

.head-default {
    font-family: 'ArialMT', 'Arial', sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: 13px;
    letter-spacing: normal;
    color: #333333;
    vertical-align: none;
    text-align: center;
    line-height: normal;
    text-transform: none;
}

.nva-home {
  width: 100%;height: 405%;position: relative; background-color: #c3ebdfc4
}

.nva-head {
  width: 100%;
  height: 120px;
}

.nva-body {
  width: 100%;
  position: absolute;
  top: 110px;
}

.hr-class {
   width: 400px;
   height: 1px;
   background-color: rgb(8, 1, 1);
   border: none;

}

a.button {
			position: relative;
			color: #050000;
			text-decoration: none;
      // background-color: rgba(219,87,5,1);
      background-color: #95d1d3;
			font-family: 'Yanone Kaffeesatz';
			font-weight: 300;
			font-size: 1.2em;
			display: block;
			padding: 3px;
			-webkit-border-radius: 6px;
			-moz-border-radius: 6px;
			border-radius: 6px;
      // -webkit-box-shadow: 0px 9px 0px rgba(219,31,5,1), 0px 9px 25px rgba(0,0,0,.7);
      -webkit-box-shadow: 0px 7px 0px #89cacc, 0px 7px 20px rgba(0,0,0,.7);
			-moz-box-shadow: 0px 7px 0px #89cacc, 0px 7px 20px rgba(0,0,0,.7);
			box-shadow: 0px 7px 0px #89cacc, 0px 7px 20px rgba(0,0,0,.7);
      // margin: 100px auto;
      height: 25px;
			width: 120px;
			text-align: center;
			-webkit-transition: all .1s ease;
			-moz-transition: all .1s ease;
			-ms-transition: all .1s ease;
			-o-transition: all .1s ease;
			transition: all .1s ease;
		}

		a.button:active {
			-webkit-box-shadow: 0px 2px 0px #89cacc, 0px 2px 4px rgba(0,0,0,.9);
			-moz-box-shadow: 0px 2px 0px #89cacc, 0px 2px 4px rgba(0,0,0,.9);
			box-shadow: 0px 2px 0px #89cacc, 0px 2px 4px rgba(0,0,0,.9);
			position: relative;
			top: 6px;
		}

</style>
