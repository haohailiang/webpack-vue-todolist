<template>
	<div class="todo-body">
		<todo-header></todo-header>
		<div class="popup-todo">
			<input type="text" placeholder="接下来要做什么" v-model="todoInputValue" @keyup.enter="handleSubmit">
			<todo-item
				v-for="(item, index) of todoLists"
				:item=item
				:index=index
				:key=item
				@delitem="handleDelClick">
			</todo-item>
		</div>
		<ul class="opera-ul">
			<li>2 item left</li>
			<li>
				<span class="on">all</span>
				<span>active</span>
				<span>completed</span>
			</li>
			<li>
				clear completed
			</li>
		</ul>
		<todo-footer></todo-footer>
	</div>
</template>

<script>
import TodoHeader from './components/TodoHeader'
import TodoItem from './components/TodoItem'
import TodoFooter from './components/TodoFooter'

export default {
	data() {
		return {
			todoInputValue    : '',
			todoLists         : ['星期天', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六']
		}
	},
	components: {
		'todo-header' : TodoHeader,
		'todo-item'   : TodoItem,
		'todo-footer' : TodoFooter
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

<style scoped>
	.todo-body{
		background: #eee;
	}
	.popup-todo{
		width: 600px;
		background: #fff;
	}
	.opera-ul span{
		display: inline-block;
		line-height: 24px;
		padding: 0 10px;
		cursor: pointer;
	}
	.opera-ul span.on{
		border:1px solid red;
		border-radius: 4px;
	}
</style>
