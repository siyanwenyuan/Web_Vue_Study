<template>
  <div class="hello">


    <h1>{{ msg }}</h1>
    <slot>基础的默认内容</slot>
    <slot name="footer">footer的默认内容</slot>
    <p>props中的count{{ count }}</p>
    <button @click="handler">按钮</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  //组件通信
  //父传子props
  //子传父： 通过自定义事件处理
  props: {
    msg: String,
    count: {
      type: [String, Number],
      // default: 100
      required: true
    }
  },
  data(){
    return{
      childCount: 0
    }
  },
  methods:{
    handler(){
      this.childCount++
      //触发自定义事件
      this.$emit("child-count-change",this.childCount)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
