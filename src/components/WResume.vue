<template>
  <div class="box">
    <div class="resume">
      <div class="left">
        <div class="img">
          <img :src="msg.imgUrl" alt="img">
        </div>
        <div class="contact">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">联系方式</span>
          </div>
          <ul>
            <contact-item
              v-for="(v, i) in msg.contact"
              :key="i"
              :w-name="i"
              :w-value="v"
              />
          </ul>
        </div>
        <div class="work">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">应聘岗位</span>
          </div>
          <div class="position">
            <span>前端开发</span>
          </div>
        </div>
        <div class="evaluate">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">个人评价</span>
          </div>
          <p>{{msg.evaluate}}</p>
        </div>
      </div>
      <div class="right">
        <div class="basic">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">基本信息</span>
          </div>
          <div class="basic-msg">
            <ul>
              <li>
                <i class="iconfont icon-account-square-outlined"></i>
                <span>姓名：{{msg.basic.name}}</span>
              </li>
              <li>
                <i class="iconfont icon-xingbienan"></i>
                <span>性别：{{msg.basic.sex}}</span>
              </li>
              <li>
                <i class="iconfont icon-shijian"></i>
                <span>出生年月：{{msg.basic.birth}}</span>
              </li>
              <li>
                <i class="iconfont icon-didian"></i>
                <span>地址：{{msg.basic.addr}}</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="education">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">教育背景</span>
          </div>
          <div class="education-msg">
            <ul>
              <li>
                <i class="iconfont icon-xinghao"></i>
                <span>学校：{{msg.education.school}}</span>
              </li>
              <li>
                <i class="iconfont icon-xuexiao"></i>
                <span>学历：{{msg.education.status}}</span>
              </li>
              <li>
                <i class="iconfont icon-icon1"></i>
                <span>专业：{{msg.education.major}}</span>
              </li>
              <li>
                <i class="iconfont icon-shijian"></i>
                <span>起止时间：{{msg.education.time}}</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="skills">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">技能</span>
          </div>
          <div class="skills-msg">
            <ul>
              <li
              v-for="(v, i) in msg.skills"
              :key="i">
              {{v}}
              </li>
            </ul>
          </div>
        </div>
        <div class="projects">
          <div class="title-box">
            <i class="iconfont icon-xinghao"></i>
            <span class="title">个人项目</span>
          </div>
          <div class="projects-msg">
            <w-project
            v-for="(v, i) in msg.projects"
            class="w-project"
            :key="i"
            :name="v.name"
            :url="v.url"
            :skill="v.skill"
            :desc="v.desc"
            :result="v.result"></w-project>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import WProject from './WProject'
import ContactItem from './ContactItem'

export default {
  name: 'w-resume',
  props: {
    msg: {
      required: true,
      type: Object
    }
  },
  components: {
    WProject,
    ContactItem
  }
}
</script>

<style scoped>
@import url("~@/assets/font/iconfont.css");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
li {
  list-style: none;
}
img {
  width: 200px;
  height: 200px;
  object-fit: fill;
}
a {
  text-decoration: none;
}
/* .iconfont {
  font-size: 16px;
  vertical-align: text-top;
} */
.box {
  margin: 10px auto;
  width: 1000px;
  border: 1px solid var(--main-color);
}
.resume {
  margin: 0 auto;
  display: flex;
}
.left {
  flex: 1;
  padding: 16px;
  border-right: dashed 1px var(--main-color);
}
.contact {
  margin: 20px 0;
  padding: 5px;
}
ul .iconfont::before {
  font-size: 20px;
  margin-right: 5px;
  vertical-align: text-top;
}
.title-box {
  padding: 10px 0;
  color: var(--main-color);
}
.title-box > *, .title > *::before {
  font-size: 32px;
}
.title {
  margin-left: 5px;
}
.icon-lianjie {
  margin-left: 5px;
}
.work {
  padding: 5px;
}
.work .position {
  padding-left: 16px;
}
.evaluate {
  padding: 5px;
}
.evaluate p {
  padding: 16px;
}
.right {
  flex: 2;
  padding: 20px;
}
.basic, .education , .skills {
  border-bottom: dashed 1px var(--main-color);
}
.basic-msg, .education-msg, .skills-msg, .projects-msg {
  padding: 16px;
  padding-top: 0;
}
.basic-msg span, .education-msg span {
  line-height: 1.2;
  vertical-align: middle;
}
.basic-msg > ul, .education-msg > ul {
  display: flex;
  flex-flow: wrap;
}
.basic-msg li, .education-msg li {
  width: 50%;
}
.skills-msg {
  line-height: 1.5;
}
.skills-msg li {
  padding: 0;
}
.w-project:not(:last-child) {
  border-bottom: dashed 1px rgb(255, 211, 211);
}
.projects-msg {
  padding-top: 0;
}
</style>
