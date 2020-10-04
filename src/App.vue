<script>
import WResume from './components/WResume'
import msg from '@/assets/msg.json'

export default {
  name: 'App',
  components: {
    WResume
  },
  render: h => {
    return h('div', {
      attrs: {
        id: 'app'
      }
    }, [
      h(WResume, {
        props: {
          msg
        }
      })
    ])
  }
}
</script>

<style>
:root {
  --main-color: rgb(91, 164, 229);
}
</style>
