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
        <hr id="classClub" class="hr-class">
        <div id="u8" class="dynamic-title">
          <div id="u8_text">俱乐部动态</div>
        </div>
      </div>
      <div id="u9">
        <img :src="cultivateTianjin" class="cultivateTianjin">
      </div>
      <div id="u10"> sdfsdfsdf </div>
      <div id="u11">
        <hr id="classDynamic" class="hr-class">
        <div id="u12" class="dynamic-title">
          <div id="u12_text">全方位成长</div>
        </div>
        <div id="u13">
          <img :src="targetIdeal" class="targetIdeal">
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
export default {
  data() {
    return {
      LineLogo: LineLogo,
      ThinkBreakLogo: ThinkBreakLogo,
      cultivateTianjin: cultivateTianjin,
      targetIdeal: targetIdeal,
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
  background-color: #c3ebdfc4;
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
  left: 20%;
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
  width: 100%;height: 100%;position: relative; background-color: #c3ebdfc4
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
