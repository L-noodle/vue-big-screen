## 一、项目描述

- 一个基于 vue、datav、Echart 框架的 " **数据大屏项目** "，通过 vue 组件实现数据动态刷新渲染，内部图表可实现自由替换。边框使用 DataV 自带组件，可进行更改，详情请点击下方 DataV 文档。
- 项目部分区域使用了全局注册方式，增加了打包体积，在实际运用中请使用**按需引入**。
- 项目环境：vue-cli-3.0、webpack-4.0、npm-6.13、node-v12.16.

友情链接：

1.  [DataV 官方文档（建议使用之前先浏览）](http://datav.jiaminghi.com/guide/)
2.  [echarts 实例](https://www.echartsjs.com/examples/zh/index.html)，[echarts 官方文档](https://www.echartsjs.com/zh/option.html#title)
3.  [Vue 官方文档](https://cn.vuejs.org/v2/guide/instance.html)
4.  [项目 gitee 地址（国内速度快）](https://gitee.com/MTrun/big-screen-vue-datav)

项目截图（展示动态）
[外链图片转存失败,源站可能有防盗链机制,建议将图片保存下来直接上传(img-KghnpAbJ-1585577359810)(https://images.gitee.com/uploads/images/2020/0318/220710_4b0bf590_4964818.png "JPW8NE}N@Y{HLYA$ZPY%T24.png")]

## 二、主要文件介绍

| 文件                | 作用/功能                                           |
| ------------------- | --------------------------------------------------- |
| mian.js             | 主目录文件，全局引入了引入 vue-awesome              |
| views/ index.vue    | 项目主结构                                          |
| views/其余文件      | 界面各个区域组件（按照位置来命名）ajax 接口请求位置 |
| assets              | 静态资源目录，放置 logo 与背景图片                  |
| assets / style.scss | 通用 CSS 文件，全局项目快捷样式调节                 |
| assets / index.scss | Index 界面的 CSS 文件                               |
| components/echart   | 所有 echart 图表（按照位置来命名）                  |

## 三、使用介绍

1. **如何请求数据**
   现在的项目未使用前后端数据请求，建议使用 axios 进行数据请求，在 main.js 位置进行全局配置，在 views/xx.vue 文件里进行前后端数据请求。

- axios 的 main.js 配置参考范例（因人而异）

```js
import axios from "axios";

//把方法放到vue的原型上，这样就可以全局使用了
Vue.prototype.$http = axios.create({
  //设置20秒超时时间
  timeout: 20000,
  baseURL: "http://172.0.0.1:80080" //这里写后端地址
});
```

- 在 vue 页面中调用 axios 方法并通过 props 传给 echarts 图表子组件

```js
export default {
  data() {
  	ListDataSelf:[]
  },
  mounted() {
   this.fetchList(); //获取数据
  },
  methods: {
	async fetchList(){
	  const { code,listData }= await this.$http.get("xx/xx/xx"x);
	  if(code === 200){
		 this.ListDataSelf= listData;
	  }
	}
  }
 }
```

2. **如何动态渲染图表**
   在`components/echart`下的文件，比如`drawPie()`是渲染函数，`echartData`是需要动态渲染的数据，当外界通过`props`传入新数据，我们可以使用`watch()`方法去监听，一但数据变化就调用`this.drawPie()`并触发内部的`.setOption`函数，重新渲染一次图表。

```js
//这里是子组件内部

props: ["listData"],
watch: {
  listData(newValue) {
     this.echartData= newValue;
     this.drawPie();
   },
  },
methods: {
  drawPie() {
  	.....
  	渲染节点名称.setOption(option);
  }
 }
```

3. **如何更换边框**
   边框是使用了 DataV 自带的组件，如：

```js
<dv-border-box-1></dv-border-box-1>
```

只需要去 views 目录下去寻找对应的位置去查找并替换就可以，具体的种类请去 DavaV 官网查看

4. **如何更换图表**
   直接进入 components/echart 下的文件修改成你要的 echarts 模样，可以去[echarts 官方社区]里面查看文件(https://gallery.echartsjs.com/explore.html#sort=rank~timeframe=all~author=all)

## 四、更新情况

如果大家有意见请进行评论，我也会尽力去更新，自己也在前端学习的路上，欢迎交流，非常感谢！
