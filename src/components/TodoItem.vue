<template>
	<div>
		<div @click="handleDelClick" class="todo-item">
			<span class="active"></span>
			值 : {{ item }}&nbsp;&nbsp;&nbsp;序号 : {{ index }}
		</div>
	</div>
</template>

<script>
export default {
	props    : ['item', 'index'],
	data () {
		return {
			msg: 'Welcome to Your Vue.js App'
		}
	},
	methods  : {
		handleDelClick(){
			this.$emit('delitem', this.index)
		}
	}
}
</script>

<style scoped>
	.todo-item{
		cursor: pointer;
	}
	span{
		width: 40px;
		height: 40px;
		display: inline-block;
		border:1px solid red;
		border-radius: 50%;

	}
	.active{
		background-color: red;
	}
</style>
