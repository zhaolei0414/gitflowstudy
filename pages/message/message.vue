<template>
	<view>
		<text>{{msg}}</text>
		<button type="default" size="mini" @click="updateUserInfo">更新</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				    msg:'hello-uni'
			}
		},
		onLoad() {
			
		},
		methods: {
			updateUserInfo(){
				uni.getUserProfile({
					desc:'获取您的头像、昵称',
					success(res) {
						console.log(res);
					},
					fail() {
						uni.showToast({
							icon:'none',
							title:'授权失败'
						})
					}
				})
			}
		}
	}
</script>

<style>
	text {
		width: 49rpx;
		height: 49rpx;
	}
</style>
