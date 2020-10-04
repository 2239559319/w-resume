<template>
  <div id="app">
    <w-resume />
  </div>
</template>

<script>
import WResume from './components/WResume'

export default {
  name: 'App',
  components: {
    WResume
  }
}
</script>

<style>
:root {
  --main-color: #ff6666;
}
</style>
