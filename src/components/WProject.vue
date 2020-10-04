<template>
  <div class="project">
    <div class="project-title">
      <i class="iconfont icon-xuexiao_kemu"></i>
      <span>{{name}}</span>
      <a :href="url" class="iconfont icon-lianjie"></a>
    </div>
    <div class="project-msg">
      <div>
        <span class="project-sub-title">项目介绍</span>
        <div class="project-detals">
          <span>{{desc}}</span>
        </div>
      </div>
      <div>
        <span class="project-sub-title">技术栈</span>
        <div class="project-detals">
          <span>{{ skill }}</span>
        </div>
      </div>
      <div>
        <span class="project-sub-title">项目结果</span>
        <div class="project-detals">
          <div
          v-for="(v, i) in result"
          :key="i">{{ v }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'w-project',
  props: ['name', 'url', 'skill', 'desc', 'result']
}
</script>

<style scoped>
@import url("~@/assets/font/iconfont.css");
.project {
  padding: 10px;
}
a {
  text-decoration: none;
}
.iconfont::before {
  font-size: 20px; 
  margin-right: 5px;
}
.project-title {
  font-size: 20px;
  padding: 5px 0;
}
.project-title > span {
  margin-right: 5px;
  color: var(--main-color);
}
.project-sub-title {
  color: rgb(91, 164, 229);
}
.project-msg {
  padding: .3rem;
}
.project-detals {
  text-indent: 20px;
  font-size: .85rem;
}
</style>
