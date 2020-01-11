<template>
<div class="message">
	<input type="text" v-model="message">
	<button @click="sendMessage">送信</button>
</div>

</template>
<script>
	export default{
		data(){
			return {
				message: '',
				username: ''
			}
		},
		methods: {
			sendMessage(){
				this.$emit('catchMessage', this.message);
				this.message='';
				this.username='';
			}
		}
	}
</script>
<style scoped>
	.message{
		display:flex;
		height: 40px;
		max-width: 100%;
	}
	input{
		margin: 0;
		padding: 0;
		flex-basis:80%;
		max-height: 100%;
	}
	button{
		margin: 0;
		padding: 0;
		flex-basis:20%;
		max-height: 100%;
		font-size: 1.5em;
		color: #fff;
		background-color:#4F83E1; 
	}
</style>
