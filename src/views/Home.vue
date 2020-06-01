<template>
  <div class="app">
    <div class="box">
      <div class="top">
        <div class="top1">
          <a href @mouseenter="enter" @mouseleave="leave">
            <img
              src="https://static.shiyanlou.com/frontend/dist/img/9f43b00.svg"
              alt
              class="picture1"
            />
          </a>
          <div class="word1">做实验，学编程</div>
        </div>
        <div class="top2">
          <div class="top_right">
            <a href @mouseenter="enter" @mouseleave="leave" style="text-decoration: none;">
              <div>企业版</div>
            </a>
            <div class="Y-axis"></div>
            <a href @mouseenter="enter" @mouseleave="leave" style="text-decoration: none;">
              <div>学校版</div>
            </a>
          </div>
          <a href @mouseenter="enter" @mouseleave="leave" style="text-decoration: none;">
            <div class="word2">登录</div>
          </a>
          <div class="word3">
            <a href @mouseenter="enter" @mouseleave="leave" style="text-decoration: none;">
            <div style="margin-top:13px">注册</div>
            </a>
          </div>
        </div>
      </div>
      <div class="title">
        <div class="title_right">
          <div class="title_right_1">
            <div class="title_right_2 iconfont icon-jiugongge-">全部课程</div>
          </div>
          <div class="title_center">
            <div>路径</div>
            <div>训练营</div>
            <div>楼+</div>
            <div>会员</div>
            <div>社区</div>
          </div>
        </div>
        <div class="title_left">
          <input type="text" placeholder="搜索 课程/问答" class="ipt" />
          <button
            class="iconfont icon-sousuosearch82"
            style="border:none;position:relative;right:20px"
          ></button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Title from "../components/home/Title";
export default {
  data() {
    return {
      list: []
    };
  },
  components: {
    Title
  },
  methods: {
    getData() {
      axios
        .get("http://120.78.14.107/api/v2/index/categories")
        .then(res => {
          this.list = res.data;
        })
        .catch(err => {
          console.log(err);
        });
    },
    enter(item) {
      item.hover = true;
    },
    leave(item) {
      item.hover = false;
    }
  },
  mounted() {},
  watch: {},
  computed: {}
};
</script>

<style scoped>
a{}
a:hover {
  color: #08bf91;
}
.app {
  display: flex;
  justify-content: center;
  background: #f9f9f9;
}
.box {
  width: 1200px;
}
.top {
  height: 80px;
  display: flex;
  justify-content: space-between;
  align-content: center;
  margin-top: 25px;
}
.picture1 {
  width: 133px;
  height: 50px;
}
.Y-axis {
  height: 15px;
  width: 1px;
  background: black;
  position: relative;
  top: 3px;
}
.top1 {
  height: 80px;
  width: 500px;
  display: flex;
  align-content: center;
}
.word1 {
  font-size: 18px;
  color: #274a59;
  margin-top: 13px;
}
.top2 {
  width: 300px;
  height: 80px;
  display: flex;
  justify-content: space-around;
}
.top_right {
  width: 120px;
  height: 30px;
  display: flex;
  justify-content: space-around;
  margin-top: 13px;
  
}
.word2 {
  color: #08bf91;
  width: 82px;
  height: 30px;
  display: flex;
  justify-content: space-around;
  margin-top: 13px;
}
.word3 {
  color: #fff;
  background: #08bf91;
  width: 82px;
  height: 48px;
  display: flex;
  justify-content: space-around;
  align-content: center;
}
.title {
  width: 1200px;
  height: 60px;
  background: #ffffff;
  display: flex;
  justify-content: space-between;
}
.title_right {
  width: 650px;

  display: flex;
  justify-content: space-around;
  align-content: center;
}
.title_right_1 {
  width: 300px;
  background: #08bf91;
  display: flex;
  justify-content: space-around;
}
.title_right_2 {
  width: 200px;
  height: 20px;
  margin-top: 16px;
  color: #ffffff;
  font-size: 18px;
}
.title_center {
  width: 350px;
  font-size: 20px;
  display: flex;
  justify-content: space-around;
  margin-top: 15px;
}
.title_left {
  width: 200px;
}
.ipt {
  height: 25px;
  margin-top: 15px;
  border-radius: 5px;
  border: gray 1px solid;
}
</style>