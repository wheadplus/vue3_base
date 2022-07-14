<template>
  <div>
    <h2>setup and ref 例子</h2>
    <div>
    {{count}}
  </div>
  <br>
  <button @click="updateCount">++</button>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'App',
  setup() {
    //变量
    // let count = 0 此时的数据非响应式数据(响应式数据，数据修改页面跟着渲染变化)
    let count = ref(0)
    // ref是个函数，作用：定义一个响应式的数据，返回一个ref对象，
    // 对象中有个value,需要修改数据，使用该ref对象调用value属性方式进行数据修改
    //方法
    function updateCount () {
      console.log(count)
      // count++ ref下++报错，因为此时count输出是ref对象，不能进行++操作
      count.value++
    }
    return {
      count,
      updateCount
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
