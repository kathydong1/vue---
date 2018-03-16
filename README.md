$on
监听当前实例上的自定义事件。事件可以由vm.$emit触发。回调函数会接收所有传入事件触发函数的额外参数。

简单的来说，就是在一个位置使用$on来定义一个函数，这个函数的名字以及方法都是按照自己的需求来进行的，然后在想要触发这个函数的时候，就可以使用$.emit来使用

一个简单的例子：

  <div id="app">
        <button @click="mathe">go</button>
    </div>
    <script src="../base/vue.js"></script>
    <script src="https://cdn.bootcss.com/vue-resource/1.3.4/vue-resource.min.js"></script>
    <script>
        var vm = new Vue({
            el:"#app",
            data:{
             
            },
            mounted:function(){
                this.$on("alert",function() {
                    alert(1)
                })
            },
            methods:{
              mathe:function() {
                  this.$emit("alert")
              }
            }
        })
    </script>
上面的函数创建的方法是点击按钮的时候弹出一个1的提示框（mounted是Vue的生命周期的一个函数，类似于react中的ComponentDidMount）

$emit
这个函数的作用就是触发使用$on创建的函数，他的出现一定是和$on一起的

$once
监听一个自定义事件，但是只触发一次，在第一次触发之后移除监听器。

上面的几种方法既可以在Vue之中创建，也可以直接挂载在Vue的实例上
