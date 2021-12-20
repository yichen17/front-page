# vue学习
## 总结 summary

### 特殊note

```html
1、修饰符可以连用
// 先阻止默认事件，在阻止冒泡
<button @click="show">
   <a href="http://www.baidu.com" @click.prevent.stop="show">335454345</a>
</button>
show(){
   alert("点击提示");
}
// 以及按键   指定 ctrl+y才生效
<input type="text" placeholder="按下回车提示输入" @keyup.ctrl.y="showInfo">
showInfo(e){
	console.log(e.key,e.keyCode); // 打印 key 和 keyCode ，如果是两个单次，示例CapsLock 则需要切换成 caps-lock
}
```





### 插值语法
```
{{ name }}  // 用于解析标签体内容，例如 <h1></h1>
```
### 指令语法
```
v-bind  // 用于解析标签(标签属性等)  例如 <a v-bind:href></a>
```
### 数据绑定
#### 单向绑定
v-bind
#### 双向绑定
v-model  只能用于输入类表单元素 value 属性

### 事件处理

> v-on 或者 @   示例  =>  v-on:click()      @click()

#### 事件修饰符

> 1、prevent：阻止默认事件    例：url 不让跳转
>
> 2、stop：阻止事件冒泡   例：不让父容器触发
>
> 3、once：事件只触发一次   例：按钮只能点击一次
>
> 4、capture：使用事件的捕获模式   例：让事件在捕获阶段触发，而不是默认的冒泡阶段
>
> 5、self：只有event.target 是当前操作的元素时才触发事件    例：只有触发元素才生效
>
> 6、passive：事件的默认行为立即执行，无需等待事件回调执行完毕   例：scroll 先执行滚动条滚动，后执行函数运算

### vue绑定 html标签
> 1、 el:绑定 例 el:'#root'
> 2、 x.$mount() 例 x.$mount('#root')
### 按键别名

>  回车 =》 enter
>
> 删除 =》 delete
>
> 退出 =》 esc
>
> 空格 =》 space
>
> 换行 =》 tab
>
> 上 =》 up
>
> 下 =》 down
>
> 左 =》 left
>
> 右 =》 right
>
> 示例： input输入框按回车输入里面的内容 
>
> <input type="text" placeholder="按下回车提示输入" @keyup.enter="showInfo">
>
> methods: {
>
> ​      showInfo(e){
>
> ​        // if(e.keyCode !== 13)return; 
>
> ​        console.log(e.target.value);
>
> ​      }
>
> ​    }



## 开发工具
### vs code
#### 常用插件
> open in brouser   //  打开页面
> HTML Snippets  // 提示 html 标签
> Live Server // 默认开启本机服务器  内置服务器
> vue  // vue  语法高亮
> Vue 3 Snippets  // vue 标签提示
>
> Tabout   // 跳括号、引号等，跟 idea tab键类似功能
>
> JavaScript (ES6) code snippets
>
> HTML CSS Support

==待尝试==

> Bracket Jumper // 快速跳括号



#### 常用快捷键 
+ 换行 ctrl+ enter
+ html 页面   按`!`，然后按`tab` 会填充html的基本内容
+ 选中多行，或者多行同时输入，  `alt`键

#### vs code 自定义模板

[参考](https://blog.csdn.net/weixin_44592912/article/details/97641835)

> file > preferences  > user snippets      // 或者  文件 >  首选项  > 用户片段
>
> 输入 html ，选择 html.json

<img src="./images/2021-12-19-1.jpg" alt="参考步骤" style="zoom: 80%;" />

##### vue 模板

```json
// 引用方式   在.html文件中，输入prefix前缀然后按 tab键即可
//    /t 相当于 tab
{
    "Print to console": {
        "prefix": "vue",
        "body": [	
			"<div id='yichen'>",
			"",
    		"</div>",

            "<template id=''>",
			"\t<div >",
			"\t",
			"\t</div>",
            "</template>",
			"",
			"<script src='/node_modules/vue/dist/vue.js'></script>",
			"<script src='/node_modules/vue-resource/dist/vue-resource.js'></script>",
			"<script src='/node_modules/vue-router/dist/vue-router.js'></script>",
            "<script>",
            "",
			"var vm=new Vue({",
			"\tel:'#yichen',",
            
			"\tdata: {",
			"\t",
			"\t},",
            "\tmethods: {",
            "\t",
            "\t},",
			"\tdirectives: {",
			"\t",
			"\t},",
			"\tcomponents: {",
			"\t",
			"\t},",
			"\tfilters: {",
			"\t",
			"\t},",
            "})",
            "</script>",

        ],
        "description": "vue template"
    }
}
```

