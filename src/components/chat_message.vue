<template>
<div class="conversation" v-bind:class="user">
		<div class="chat_box">
			<p class="message">{{ speaker }}</p>
		</div>
		<img :src="img_src()" alt="" />
	</div>

</template>
<script>
export default {
	data() {
		return {
//			img_src:function(){
//				
//				return require('../assets/bot.jpeg');
//			}
//			img_src:require('../assets/.jpeg')
			
		};
	},
	props: {
		speaker: {
			type: String,
			required: true
		},
		user: {
			type: String,
			required: true,
			validator (val) {
				return ['my', 'other'].includes(val)
			}
			
		},
		img:{
			type: String,
			required: true
		}
	},
	methods: {
		img_src:function(){
			return require('../assets/'+this.img+'.png');
		}
		
	}
	
};
</script>
<style scoped>
	.my {
	border-color: 1px solid #696969;
	color: aqua;
	background-color: transparent;
	display: flex;
	margin-bottom: 10px;
	justify-content: flex-end;
}
	.my img {
	border-radius: 100%;
	background-color: aliceblue;
	width: 75px;
	height: 75px;
	margin: 10px 20px;
}
	.my >.chat_box {
	position: relative;
	display: inline-block;
	margin: 1.5em 0 1.5em 15px;
	padding: 7px 10px;
	min-width: 120px;
	max-width: 100%;
	color: #555;
	font-size: 16px;
	background: #85ff49;
	box-sizing: border-box;
	border-radius: 50%;
}

	.my >.chat_box:before {
	content: "";
	position: absolute;
	top: 40%;
	right: -14px;
	margin-top: -12px;
	border-bottom: 30px solid transparent;
	border-left: 30px solid #85ff49;
	z-index: 2;
}
	
	
	.other {
		border-color: 1px solid #696969;
		color: aqua;
		background-color: transparent;
		display: flex;
		margin-bottom: 10px;
	}
	.other img {
		border-radius: 100%;
		background-color: aliceblue;
		width: 75px;
		height: 75px;
		margin: 10px 20px;
		order: 1;
	}
	
	.other >.chat_box {
		position: relative;
		display: inline-block;
		margin: 1.5em 0 1.5em 15px;
		padding: 7px 10px;
		min-width: 120px;
		max-width: 100%;
		color: #555;
		font-size: 16px;
		background: #ffffff;
		box-sizing: border-box;
		border-radius: 50%;
		order: 2;
	}

	.other >.chat_box:before {
		content: "";
		position: absolute;
		top: 40%;
		left: -14px;
		margin-top: -12px;
		border-bottom: 30px solid transparent;
		border-right: 30px solid #ffffff;
		z-index: 2;
	}

</style>
