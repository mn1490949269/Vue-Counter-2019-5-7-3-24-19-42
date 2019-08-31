<template>
  <div>
  <p>click {{count}} times,count is {{oddOrEven}}</p >
  <button @click="inc">button</button>
  <button @click="dec">button</button>
  <button @click="incIfOdd">button</button>
  <button @click="incSetTimeout">button</button>
 </div>
</template>

<script>
 export default {
  data() {
   return {
    count: 0
   }
  },
  computed: {
   oddOrEven() {
    return this.count % 2 === 0 ? '偶数' : '奇数' //使用三目运算符判断count是奇数还是偶数，渲染对应的数据
   }
  },
  methods: {
   //增加
   inc() {
    const count = this.count
    this.count = count + 1
   },
   //减少
   dec() {
    const count = this.count
    this.count = count - 1
   },
   //奇数增加
   incIfOdd() {
    const count = this.count
    if (count % 2 === 1) {
     this.count = count + 1
    }
   },
   //异步增加
   incSetTimeout() {
    setTimeout(() => {
     const count = this.count
     this.count = count + 1
    }, 1000)
   }
  },
 }
</script>