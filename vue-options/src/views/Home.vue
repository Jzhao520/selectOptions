<template>
  <div class="home">
    <div class="row">
		<select-options :data="list1" :status.sync="list1_Status" :init="list1_Status.content"></select-options>
	</div>
	<div class="row">
		<select-options :data="list2" :status.sync="list2_Status" :init="list2_Status.content"></select-options>
	</div>
  </div>
</template>

<script>
// @ is an alias to /src
import options from '@/components/options.vue'

export default {
	name: 'Home',
	components: {
		"select-options" : options
	},
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
}
</script>
