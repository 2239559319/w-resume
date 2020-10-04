<template>
  <li>
    <template v-if="wName === 'phone'">
      <i class="iconfont icon-shouji1"></i>
      <span>phone：{{ wValue }}</span>
    </template>
    <template v-else-if="wName === 'email'">
      <i class="iconfont icon-youxiang"></i>
      <span>邮箱：{{ wValue }}</span>
    </template>
    <template v-else-if="wName === 'github'">
      <i class="iconfont icon-github"></i>
      <span>github：{{ wValue.name }}</span>
      <a :href="wValue.url" class="iconfont icon-lianjie"></a>
    </template>
    <template v-else-if="wName === 'npm'">
      <i class="iconfont icon-npm"></i>
      <span>npm：{{ wValue.name }}</span>
      <a :href="wValue.url" class="iconfont icon-lianjie"></a>
    </template>
    <template v-else>
      <i class="iconfont icon-xinghao"></i>
      <span>{{ wName }} ：{{ wValue }}</span>
    </template>
  </li>
</template>
<script>
export default {
  props: {
    wName: {
      required: true,
      type: String,
    },
    wValue: {
      required: true,
      type: Object | String,
    }
  }
}
</script>

<style scoped>
@import url('~@/assets/font/iconfont.css');
li {
  list-style: none;
}
a {
  text-decoration: none;
}
.iconfont::before {
  font-size: 20px;
  margin-right: 5px;
  vertical-align: middle;
}
.icon-lianjie {
  margin-left: 5px;
}
</style>
