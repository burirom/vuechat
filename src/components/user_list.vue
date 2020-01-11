<template>
	<div class="friend_list">
		<div v-for="user_list in user_lists" :key="user_list.id">
			{{ user_list.name }}
		</div>
	</div>
</template>
<script>
export default {
	data() {
		return {
			user_lists: [
				{ name: "いちご" },
				{ name: "りんご" },
				{ name: "みかん" },
				{ name: "ぶどう" }
			]
		};
	},
	methods: {
		friend_name() {}
	}
};
</script>
<style scoped>
.friend_list {
	background: #ffffff;
	height: 100%;
	width: 100%;
}
</style>
