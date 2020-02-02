<template>
	<div id="app">
		<chat_form @catchMessage="displayMessage" class="chat_form"></chat_form>
		<chat_message
			v-for="chat in chatLog"
			:speaker="chat.speaker"
			:key="chat.id"
			:user="chat.user"
			:img="chat.img"
			
		></chat_message>
	</div>
</template>

<script>
import chat_form from "./components/chat_form.vue";
import chat_message from "./components/chat_message.vue";


export default {
	name: "app",
	components: {
		chat_form,
		chat_message
	},
	data() {
		return {
			chatLog: []
		};
	},
	methods: {
		displayMessage(message) {
			this.chatLog.push({
				speaker: message,
				user : 'my',
				img : 'logo'
			});
			setTimeout(this.botsubmit,1000);
		},
		
		botsubmit(){
			this.chatLog.push({
				speaker: 'Hello Vue!!',
				user : 'other',
				img:'bot'
			});
		}
	}
};
</script>

<style>
#app {
	font-family: "Avenir", Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 10px;
	
}
	.chat_form{
		position: fixed;
		width: 100%;
		bottom: 0px;
		right: 0px;
		justify-content: flex-end;
	}

	
</style>
