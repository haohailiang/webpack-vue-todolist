<template>
	<div>
		<div @click="handleDelClick">
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

</style>
