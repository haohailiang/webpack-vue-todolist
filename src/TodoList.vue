<template>
	<div>
		<input type="text" v-model="todoInputValue" @keyup.enter="handleSubmit">
		<todo-item
			v-for="(item, index) of todoLists"
			:item=item
			:index=index
			:key=item
			@delitem="handleDelClick">
		</todo-item>
	</div>
</template>

<script>
import TodoItem from './components/TodoItem'

export default {
	data() {
		return {
			todoInputValue    : '',
			todoLists         : ['星期天', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六']
		}
	},
	components: {
		'todo-item' : TodoItem
	},
	methods: {
		handleSubmit(){
			this.todoLists.push(this.todoInputValue);
			this.todoInputValue = '';
		},
		handleDelClick(index){
			this.todoLists.splice(index, 1);
		}
	}
}
</script>

<style>

</style>
