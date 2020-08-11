# selectOptions
+ 这是一个移动端模拟表单select功能的组件，基于vue2.0
> 部分js来自于开源 vue-select组件
[传送门](https://github.com/sagalbot/vue-select "vue-select")

```
   // content不存在的时候，组件中默认展示请选择
   data(){
		return {
			list1 : [
				{id :1 ,default:'习大大'},
				{id :2 ,default:'普京'},
				{id :3 ,default:'特不朗谱'}
			],
			list1_Status :{
				index :''
			},
			list2 : [
				{id :1 ,default:'中国'},
				{id :2 ,default:'俄罗斯'},
				{id :3 ,default:'美国'}
			],
			list2_Status :{
				content:'中国', 
				index :'0'
			}
		}
	}
```
> ![组件预览](http://m.qpic.cn/psc?/V12VYUx50nnP3h/TmEUgtj9EK6.7V8ajmQrEBJ13R1PYSajYO6.Jksp80SWOtBuxyk33K3t41Rdy7s9yshPoyYggfZUwBRi7WsV4nV3duixwYhmjGxeHAqIm.Y!/b&bo=UAFKAQAAAAACFyk!&rf=viewer_4 "组件预览")
