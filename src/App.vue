<template>
  <div class="container">
    <global-header :user="user"></global-header>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
const testData: ColumnProps[] = [
  {
    id: 1,
    title: '这是专栏1',
    desc: '这是专栏1,采用vue3+ts开发非常有趣',
    avatar: 'https://img10.360buyimg.com/n1/s450x450_jfs/t1/113838/11/13681/59995/5f1fb65dE13c92464/4641de4f63536997.jpg'
  },
  {
    id: 2,
    title: '这是专栏2',
    desc: '这是专栏2,采用vue3+ts开发非常有趣',
    avatar: 'https://img10.360buyimg.com/n1/s450x450_jfs/t1/113838/11/13681/59995/5f1fb65dE13c92464/4641de4f63536997.jpg'
  },
  {
    id: 3,
    title: '这是专栏3',
    desc: '这是专栏3,采用vue3+ts开发非常有趣',
    avatar: 'https://img10.360buyimg.com/n1/s450x450_jfs/t1/113838/11/13681/59995/5f1fb65dE13c92464/4641de4f63536997.jpg'
  },
  {
    id: 4,
    title: '这是专栏4',
    desc: '这是专栏4,采用vue3+ts开发非常有趣',
    avatar: 'https://img10.360buyimg.com/n1/s450x450_jfs/t1/113838/11/13681/59995/5f1fb65dE13c92464/4641de4f63536997.jpg'
  },
  {
    id: 5,
    title: '这是专栏5',
    desc: '这是专栏5,采用vue3+ts开发非常有趣',
    avatar: ''
  }
]
const currentUser: UserProps = {
  isLogin: true,
  name: 'lemon'
}
export default defineComponent({
  name: 'Home',
  components: {
    ColumnList,
    GlobalHeader
  },
  setup() {
    return {
      list: testData,
      user: currentUser
    }
  }
})
</script>
